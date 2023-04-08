# Meu código fonte
# teste-de-target-sistemas--gabriel-lopes


// #questão 2: A função "verificaFibonacci" recebe um número como entrada e verifica se esse número pertence à sequência de Fibonacci. Ela retorna uma mensagem indicando se o número pertence ou não à sequência.

+function verificaFibonacci(numero) {
  let a = 0;
  let b = 1;

  while (b <= numero) {
    if (b === numero) {
      return `O número ${numero} pertence à sequência de Fibonacci.`;
    }

    const temp = b;
    b = a + b;
    a = temp;
  }

  return `O número ${numero} não pertence à sequência de Fibonacci.`;
}

console.log(verificaFibonacci(5)); // O número 5 pertence à sequência de Fibonacci.
console.log(verificaFibonacci(7)); // O número 7 não pertence à sequência de Fibonacci.


// #questão 3: A função "calculaFaturamento" recebe um array de números que representam o faturamento diário de uma empresa. Ela retorna um objeto com informações sobre o faturamento, incluindo o menor e o maior valor, a quantidade de dias em que o faturamento foi acima da média, e a média de faturamento diário.

const faturamentoDiario = [1000, 1200, 800, 1500, 2000, 3000, 600, 0, 0, 1000, 1300, 1400, 2000, 2500, 1800, 2200, 1000, 800, 1200, 1500, 900, 0, 0, 2500, 3000, 1800, 2200, 2000, 1500, 1000];

function calculaFaturamento(faturamento) {
  let menorValor = faturamento[0];
  let maiorValor = faturamento[0];
  let somaFaturamento = 0;
  let diasAcimaMedia = 0;

  for (let i = 0; i < faturamento.length; i++) {
    if (faturamento[i] < menorValor) {
      menorValor = faturamento[i];
    }

    if (faturamento[i] > maiorValor) {
      maiorValor = faturamento[i];
    }

    somaFaturamento += faturamento[i];
  }

  const mediaFaturamento = somaFaturamento / faturamento.length;

  for (let i = 0; i < faturamento.length; i++) {
    if (faturamento[i] > mediaFaturamento) {
      diasAcimaMedia++;
    }
  }

  return {
    menorValor,
    maiorValor,
    diasAcimaMedia
  };
}

console.log(calculaFaturamento(faturamentoDiario)); // { menorValor: 0, maiorValor: 3000, diasAcimaMedia: 13 }


// #questão 4: A função "calculaPercentualFaturamento" recebe um objeto com o faturamento mensal de cada estado de uma empresa. Ela retorna um objeto com as porcentagens de faturamento de cada estado em relação ao faturamento total da empresa.

const faturamentoMensal = {
  SP: 67836.43,
  RJ: 36678.66,
  MG: 29229.88,
  ES: 27165.48,
  Outros: 19849.53
};

function calculaPercentualFaturamento(faturamento) {
  const totalFaturamento = Object.values(faturamento).reduce((acc, valor) => acc + valor);
  const percentuais = {};
  for (const [estado, valor] of Object.entries(faturamento)) {
    percentuais[estado] = (valor / totalFaturamento) * 100;
  }
  return percentuais;
}

console.log(calculaPercentualFaturamento(faturamentoMensal));


// #questão 5: A função "inverteString" recebe uma string como entrada e retorna a mesma string invertida.
  function inverteString(str) {
  let novaString = '';
  for (let i = str.length - 1; i >= 0; i--) {
    novaString += str[i];
  }
  return novaString;
}
