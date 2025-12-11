<!DOCTYPE html>
<html lang="zh-Hant">
<head>
  <meta charset="UTF-8">
  <title>質數計算機</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px;
      background-color: #114514; 
    }
    h1 {
      color: #000000;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
    }
    #log {
      margin-top: 20px;
      white-space: pre-line;
      background: #fff;
      padding: 15px;
      border: 1px solid #ccc;
    }
  </style>
</head>
<body>

<h1>質數計算機</h1>
<p>請輸入六位以內的數字：</p>
<input type="text" id="prime" maxlength="6">
<button onclick="count()">計算</button>
<button onclick="reflash()">重設結果</button>

<div id="log"></div>

<script>
  function count() {
    const input = document.getElementById('prime');
    const value = input.value.trim();
    const n = Number(value);

    if (n.length >= 6) {
      alert("請輸入六位以內數字！");
      return;
    }

    let factor = 0, a = Math.sqrt(prime);


    for (let n = 1; n < a; n++) {
      if (prime % n === 0) {
        factor++;
      }       
    }


    const logDiv = document.getElementById('log');
    if (factor === 2) {
      logDiv.innerText += `${prime} 是一個質數`;
    }else
      logDiv.innerText += `${prime} 是一個合數 有${factor}個因數`;

    input.value = '';
    input.focus();
  }

  function reflash() {
    document.getElementById('prime').value = '';
    document.getElementById('log').innerText = '';
  }

</script>


</body>
</html>
