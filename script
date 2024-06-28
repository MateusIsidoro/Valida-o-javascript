const pwd = document.getElementById("pwd");
const pwd2 = document.getElementById("pwd2");
const nasc = document.getElementById("nasc");
const idade = document.getElementById("idade");
const tel = document.getElementById("tel")


function validate(item){
    item.setCustomValidity('');
    item.checkValidity();

    if (item == pwd2){
        if (item.value == pwd.value){
            item.setCustomValidity('');
        }  
        else{
            item.setCustomValidity('As senha não batem!');
        }
    }

    if (item == nasc){
        let hoje = new Date();
        let dnasc = new Date(nasc.value);

        let valorIdade = hoje.getFullYear() - dnasc.getFullYear();
        let dm = hoje.getMonth() - dnasc.getMonth();
        if (dm < 0 || (dm == 0 && hoje.getDate() < dnasc.getDate())){
            valorIdade--;
        }
        idade.value = valorIdade + " anos";
        if (valorIdade > 100){
            item.setCustomValidity("Mentir é feio!")
        }else if (valorIdade < 0){
            item.setCustomValidity("Ué! Você não nasceu ainda?")
        }else if (valorIdade < 14){
            item.setCustomValidity("Você precisa ter pelo menos 14 anos de idade para jogar o jogo")
        }else{
            item.setCustomValidity("")
        }
    }
}

function maskTel(){
    let strTel = tel.value;
    if (strTel.length == 2){
        tel.value = "(" + tel.value + ") ";
    }else if (strTel.length == 9){
        tel.value = tel.value + "-";
    }
}


pwd.addEventListener("input", function(){validate(pwd)});
pwd2.addEventListener("input", function(){validate(pwd2)});
nasc.addEventListener("input", function(){validate(nasc)});
tel.addEventListener("input", maskTel);

pwd.addEventListener('invalid', function(){
    if(pwd.value == ""){
        pwd.setCustomValidity("Insira uma senha!")
    }
    else{
        pwd.setCustomValidity("A senha precisa conter pelo menos 8 caracteres: um número, uma letra minúscula e uma letra maiúscula")
    }
})