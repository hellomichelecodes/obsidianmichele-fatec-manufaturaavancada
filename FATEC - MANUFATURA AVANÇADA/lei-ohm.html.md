<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simulador da Lei de Ohm</title>
<style>
    body{
        font-family: Arial, sans-serif;
        background:#1e1e1e;
        color:white;
        display:flex;
        justify-content:center;
        align-items:center;
        min-height:100vh;
        margin:0;
    }
    .container{
        background:#2a2a2a;
        padding:25px;
        border-radius:12px;
        width:360px;
        box-shadow:0 0 15px rgba(0,0,0,.4);
    }
    h2{
        text-align:center;
        color:#4fc3f7;
    }
    label{
        display:block;
        margin-top:15px;
        margin-bottom:5px;
    }
    select,input{
        width:100%;
        padding:10px;
        border-radius:8px;
        border:none;
        font-size:16px;
    }
    button{
        margin-top:20px;
        width:100%;
        padding:12px;
        background:#4fc3f7;
        color:black;
        font-weight:bold;
        border:none;
        border-radius:8px;
        cursor:pointer;
        font-size:16px;
    }
    button:hover{
        background:#29b6f6;
    }
    #resultado{
        margin-top:20px;
        padding:15px;
        background:#111;
        border-radius:8px;
        text-align:center;
        font-size:18px;
        color:#81c784;
    }
</style>
</head>
<body>

<div class="container">
    <h2>Lei de Ohm</h2>

    <label>Calcular:</label>
    <select id="tipo" onchange="atualizarCampos()">
        <option value="V">Tensão (V)</option>
        <option value="I">Corrente (I)</option>
        <option value="R">Resistência (R)</option>
    </select>

    <div id="campos"></div>

    <button onclick="calcular()">Calcular</button>

    <div id="resultado">Resultado aparecerá aqui</div>
</div>

<script>
function atualizarCampos(){
    const tipo = document.getElementById("tipo").value;
    const campos = document.getElementById("campos");

    if(tipo === "V"){
        campos.innerHTML = `
            <label>Corrente (A):</label>
            <input type="number" id="i" step="any">
            <label>Resistência (Ω):</label>
            <input type="number" id="r" step="any">
        `;
    }
    if(tipo === "I"){
        campos.innerHTML = `
            <label>Tensão (V):</label>
            <input type="number" id="v" step="any">
            <label>Resistência (Ω):</label>
            <input type="number" id="r" step="any">
        `;
    }
    if(tipo === "R"){
        campos.innerHTML = `
            <label>Tensão (V):</label>
            <input type="number" id="v" step="any">
            <label>Corrente (A):</label>
            <input type="number" id="i" step="any">
        `;
    }
}

function calcular(){
    const tipo = document.getElementById("tipo").value;
    let resultado = "";

    if(tipo === "V"){
        const i = parseFloat(document.getElementById("i").value);
        const r = parseFloat(document.getElementById("r").value);
        if(isNaN(i) || isNaN(r)) return mostrarErro();
        resultado = `Tensão (V) = ${(i*r).toFixed(2)} V`;
    }

    if(tipo === "I"){
        const v = parseFloat(document.getElementById("v").value);
        const r = parseFloat(document.getElementById("r").value);
        if(isNaN(v) || isNaN(r) || r===0) return mostrarErro();
        resultado = `Corrente (I) = ${(v/r).toFixed(2)} A`;
    }

    if(tipo === "R"){
        const v = parseFloat(document.getElementById("v").value);
        const i = parseFloat(document.getElementById("i").value);
        if(isNaN(v) || isNaN(i) || i===0) return mostrarErro();
        resultado = `Resistência (R) = ${(v/i).toFixed(2)} Ω`;
    }

    document.getElementById("resultado").innerHTML = resultado;
}

function mostrarErro(){
    document.getElementById("resultado").innerHTML =
        "Preencha valores válidos.";
}

atualizarCampos();
</script>

</body>
</html>