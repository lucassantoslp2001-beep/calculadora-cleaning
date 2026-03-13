<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Calculadora de House Cleaning</title>
<style>
body { font-family: Arial, sans-serif; max-width: 500px; margin: 40px auto; }
h2 { color: #333; }
label { display: block; margin-top: 10px; }
input, select { width: 100%; padding: 5px; margin-top: 3px; }
button { margin-top: 15px; padding: 10px 20px; font-size: 16px; cursor: pointer; }
.resultado { margin-top: 20px; padding: 15px; background: #f0f0f0; border-radius: 5px; }
</style>
</head>
<body>

<h2>Calculadora de House Cleaning</h2>

<label>Quartos:</label>
<input type="number" id="quartos" value="1" min="1" max="4">

<label>Banheiros:</label>
<input type="number" id="banheiros" value="1" min="0" max="6">

<label>Pets:</label>
<input type="number" id="pets" value="0" min="0" max="10">

<button onclick="calcular()">Calcular Preços</button>

<div class="resultado" id="resultado">
<p>Preencha os campos e clique em "Calcular Preços".</p>
</div>

<script>
function calcular() {
    let q = parseInt(document.getElementById('quartos').value);
    let b = parseInt(document.getElementById('banheiros').value);
    let p = parseInt(document.getElementById('pets').value);

    // Preço base por quartos
    let base = q==1?120:q==2?145:q==3?170:q==4?195:0;

    // Ajuste por banheiro
    let banho = (b-q==1)?5:(b-q==-1)?-5:0;

    // Ajuste por pets
    let pet = p*10;

    // Função para calcular final com frequência
    function precoFinal(freq) {
        let freqAdj = freq=="Semanal"?-50:freq=="Mensal"?50:0;
        return base + banho + pet + freqAdj;
    }

    let semanal = precoFinal("Semanal");
    let quinzenal = precoFinal("Quinzenal");
    let mensal = precoFinal("Mensal");

    // Mostrar resultado
    document.getElementById('resultado').innerHTML = `
        <h3>Preços Finais:</h3>
        <ul>
            <li><strong>Semanal:</strong> $${semanal}</li>
            <li><strong>Quinzenal:</strong> $${quinzenal}</li>
            <li><strong>Mensal:</strong> $${mensal}</li>
        </ul>
        <p>(Incluindo ajuste de banheiro e pets)</p>
    `;
}
</script>

</body>
</html>
