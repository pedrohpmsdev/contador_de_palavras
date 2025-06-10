import fs from 'fs/promises';

async function ReadFile(arquivotxt) {
    try{const dados_arquivo =  await fs.readFile(arquivotxt, 'utf-8');
    return dados_arquivo;
    }
    catch(err){
        console.log(err);
        throw new Error('Erro de leitura.');
    }
}   

function countWords(dados){
    const regex = /[\p{L}\p{N}_]+(?:[.,-:][\p{L}\p{N}_]+)*/gu;
    const palavras = dados.match(regex);
    if (palavras === null){
        console.log('Nenhuma palavra encontrada no arquivo. TOTAL: 0.');
        return 0;
    }
    console.log(palavras);
    return palavras.length;
}

const dados = await ReadFile('arquivo.txt');
const dadosCorrigidos = dados.normalize('NFC');
const numero_palavras = countWords(dadosCorrigidos);
console.log(`TOTAL: ${numero_palavras}`);
