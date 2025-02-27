# SGR
É um sistema pensado nas empresas de petroléo.

# template/index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistema de Gestão de Risco e Segurança</title>
    <link rel="stylesheet" href="{{ url_for('static', filename='style.css') }}">
    
</head>
<body class="body">
    <div class="titulo">
        <h1>SGR</h1>
    </div>
    <!--Estrutra do cadastro de Risco-->
    <!--Informações básicas-->
    <form action="app.py" method="post"> 
    </div>
    <!---Carrosel-->
    <div class="container">
      <div class="carrossel">

        <!--ID de risco-->
        <article class="card"><div class="ID">
          <label for="ID_de_risco">ID de Risco</label>
          <input type="text" id="ID_de_risco name="ID_de_risco>
         
        <!--nome de risco-->
        <label for="Nome_do_Risco">Nome do Risco:</label>
      <input type="text" id="Nome_do_Risco" name="Nome_do_Risco">
      <div class="tooltip tooltip-azul">
                                         🛈
        <span class="tooltip-text">Ex:"Vazamento de óleo na plataforma"</span>
      </div>
      </div>
      <!--categoria de risco-->
      <label for="Categoria_do_Risco">Categoria do Risco</label>
      <input type="text" id="Categoria_do_Risco" name="Categoria_do_Risco">
      <div class="tooltip tooltip-vermelho">
                                        🛈
        <span class="tooltip-text"> Ex: Ambiental, Operacional, Financeiro, Segurança, etc."</span>
      </div>
      <!--Setor afetado-->
      <label for=""Setor_afetado>Setor Afetado</label>
      <input type="text" id="Setor_afetado" name="Setor_afetado"> 
      <div class="tooltip tooltip-verde">
                                       🛈
        <span class="tooltip-text"> Ex: Perfuração, Transporte, Refino, etc.</span>
      </div>

        </article>

          <!--Avaliação de Risco-->
        <article class="card">
          <div class="avaliação_de_Risco">
            <h1>Avaliação de Risco</h1>
            <p>Escala de 1 a 5</p>
          </div>
          <div class="slider-container">
            <input type="range" min="1" max="5" value="3" class="slider" id="slider">
            <div class="value-display">
                Valor: <span id="sliderValue">3</span> - <span id="sliderText">Bom</span>
            </div>
        </div>
    </article>
<!--Severidade/Impacto-->
<article class="card">
  <div class="avaliação_de_Risco">
    <h1>Avaliação de Risco</h1>
    <p>Escala de 1 a 5</p>
  </div>
  <div class="slider-container">
    <input type="range" min="1" max="5" value="3" class="slider" id="slider">
    <div class="value-display">
        Valor: <span id="sliderValue">3</span> - <span id="sliderText">Bom</span>
    </div>
</div>
</article>
        <article class="card"></article>
    </div>
</form>
<script>
            const slider = document.getElementById("slider");
        const sliderValue = document.getElementById("sliderValue");
        const sliderText = document.getElementById("sliderText");

        // Textos correspondentes a cada valor do slider
        const textos = {
            1: "Improvável",
            2: "Pouco provável",
            3: "Possível",
            4: " Provável",
            5: "Quase certo"
        };

        // Atualiza o valor e o texto conforme o usuário arrasta o slider
        slider.addEventListener("input", function() {
            sliderValue.textContent = this.value;
            sliderText.textContent = textos[this.value];
        });
</script>
</body>
</html>

#static/style.css
body {
    font-family: Arial, sans-serif;
    background-color: #ffffff;
    text-align: center;
    padding: 20px;
}

h1 {
    color: #000000;
}
.ID{
display: grid;
gap: 10px;
width: 25%;


}
               /* Contêiner flexível para manter alinhado, mas permitir ajustes */
        .tooltip-container {
            display: flex;
            flex-direction: column;
            align-items: flex-start; /* 🔹 Ajusta para mover independentemente */
            gap: 40px; /* 🔹 Maior espaço para evitar sobreposição */
            margin: 50px;
            
        }

        /* Estilo base dos tooltips */
        .tooltip {
            position: relative;
            display: inline-block;
            cursor: pointer;
            left: 45%;
            top:-150%;
        

        }

        .tooltip .tooltip-text {
            visibility: hidden;
            width: 240px;
            text-align: center;
            padding: 5px;
            border-radius: 8px;
            position: absolute;
            opacity: 0;
            transition: opacity 0.3s;
        }

        .tooltip:hover .tooltip-text {
            visibility: visible;
            opacity: 1;
        }

        /* Tooltip Azul - Movido para esquerda */
        .tooltip-azul .tooltip-text {
            background-color: blue;
            color: white;
            left: -150px;  /* 🔹 Movido para a esquerda */
            top: 0;
        }

        /* Tooltip Vermelho - Movido para direita */
        .tooltip-vermelho .tooltip-text {
            background-color: red;
            color: white;
            left: 30px;  /* 🔹 Movido para a direita */
            top: 10px;  /* 🔹 Ajustado para baixo */
        }

        /* Tooltip Verde - Movido para cima */
        .tooltip-verde .tooltip-text {
            background-color: green;
            color: white;
            left: 50px;
            top: -40px;  /* 🔹 Movido para cima */
        }
        .container{
            max-width: 550px;
            min-width: 350px;
            margin: auto;
            display: grid;
            gap: 1.2rem;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            justify-content: center;
            padding: 2rem;
            background-color: #f0f0f0;
            border-radius: 20px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            align-items: center;


        }

        .carrossel{
            display: flex;
            grid-auto-flow: column;
            gap: 1.2rem;
            overflow-x: auto;
            overscroll-behavior-x:contain;
            align-content: center;
            
            
        }

        .card{
            background-color: rgb(7, 255, 115);
            min-height: 340px;
            min-width: 300px;
            border-radius: 60px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
            color: #333;
            scroll-snap-align: center;
           
            
        }

        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        .slider-container {
            width: 300px;
            margin: auto;
        }
        .slider {
            width: 100%;
        }
        .value-display {
            font-size: 20px;
            margin-top: 10px;
            font-weight: bold;
        }
      .avaliação_de_Risco{
        text-align: center;
        
      }
      .severidade_impacto{
        text-align: center;
        top:25%;
        left: 400px;
        position: absolute;
        }

  #app.py
  import webbrowser
import time
from flask import Flask, render_template

app = Flask(__name__, template_folder="templates")

@app.route("/")
def home():
    return render_template("index.html")

if __name__ == "__main__":
    url = "http://127.0.0.1:5000/"  # URL do servidor Flask
    
    # 🔹 Aguarda um pequeno tempo antes de abrir o navegador
    time.sleep(1)

    # 🔹 Abre no Blisk (substitua o caminho se necessário)
    webbrowser.get('"C:/Program Files/Blisk/Blisk.exe" %s').open(url)
    
    # 🔹 Inicia o Flask
    app.run(debug=True)
    print("Servidor iniciado!")

    


