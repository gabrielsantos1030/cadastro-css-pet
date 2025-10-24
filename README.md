<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadastro</title>
    <link rel="shortcut icon" href="img/favicon.ico" type="image/x-icon">
    <link rel="stylesheet" href="css/cadastro.css">
</head>
<body>
    <form>
        <div class="container">
            <div class="cadastro-form">
                <fieldset id="form-fieldset">
                    <h1>Cadastro</h1>
                    <input type="text" placeholder="Digite seu nome completo" required>
                    <input type="tel" placeholder="(00) 0000-0000" required>
                    <input type="text" placeholder="Endereço" required>
                    <input type="email" placeholder="Email" required>
                    <input type="password" placeholder="Senha" required>
                    <input type="password" placeholder="Confirmar Senha" required>
                    
                    <br>

                    <div id="pets-container">
                        <div class="pet-section">
                            <h2>Pet</h2>
                            <input type="text" placeholder="Digite o Nome do Pet" required><br>
                            <label> Sexo do pet: </label>
                            <label><input type="radio" name="Sexo1" value="Macho" required>Macho</label>
                            <label><input type="radio" name="Sexo1" value="Femea" required>Femea</label>
                            <br>
                            <label> Porte: </label>
                            <label><input type="radio" name="Porte1" value="Pequeno" required>Pequeno</label>
                            <label><input type="radio" name="Porte1" value="Medio" required>Medio</label>
                            <label><input type="radio" name="Porte1" value="Grande" required>Grande</label>
                            <br><br>
                            <select name="Raca1" required>
                                <option value="" disabled selected hidden>Escolha uma Raça</option>
                                <option value="Pincher">Pincher</option>
                                <option value="Labrador">Labrador</option>
                                <option value="Golden Retriver">Golden Retriver</option>
                                <option value="Pastor Alemao">Pastor Alemao</option>
                            </select>
                            <br><br>
                            <label for="foto">Foto do Pet</label>
                            <input type="file" name="Foto_pet1" accept="image/*" required>
                        </div>
                    </div>
                    
                    <br><br>
                    <button type="submit">Cadastrar</button>
                    <button type="reset">Limpar</button>
                    <button type="button" id="add-pet-btn">Adicionar Pet</button>
                </fieldset>
            </div>
        </div>
    </form>
        <script>
const addPetButton = document.getElementById('add-pet-btn');
const petsContainer = document.getElementById('pets-container');
let petCounter = 2;
addPetButton.addEventListener('click', () => {
    const newPetSection = document.createElement('div');
    newPetSection.classList.add('pet-section'); 
    const newPetHTML = `
        <hr>
        <h2>Pet</h2>
        <input type="text" placeholder="Digite o Nome do Pet" required><br>
        <label> Sexo do pet: </label>
        <label><input type="radio" name="Sexo${petCounter}" value="Macho" required>Macho</label>
        <label><input type="radio" name="Sexo${petCounter}" value="Femea" required>Femea</label>
        <br>
        <label> Porte: </label>
        <label><input type="radio" name="Porte${petCounter}" value="Pequeno" required>Pequeno</label>
        <label><input type="radio" name="Porte${petCounter}" value="Medio" required>Medio</label>
        <label><input type="radio" name="Porte${petCounter}" value="Grande" required>Grande</label>
        <br><br>
        <select name="Raca${petCounter}" required>
            <option value="" disabled selected hidden>Escolha uma Raça</option>
            <option value="Pincher">Pincher</option>
            <option value="Labrador">Labrador</option>
            <option value="Golden Retriver">Golden Retriver</option>
            <option value="Pastor Alemao">Pastor Alemao</option>
        </select>
        <br><br>
        <label>Foto do Pet</label>
        <input type="file" name="Foto_pet${petCounter}" accept="image/*" required>
    `;
    newPetSection.innerHTML = newPetHTML;
    petsContainer.appendChild(newPetSection);
    petCounter++;
});
    </script>
</body>
</html>
