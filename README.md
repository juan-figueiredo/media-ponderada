// Função para calcular a média ponderada
function calcularMediaPonderada(notas, pesos) {
  if (notas.length !== pesos.length) {
    throw new Error('O número de notas deve ser igual ao número de pesos.');
  }

  const somaProdutos = notas.reduce((acumulador, nota, index) => {
    return acumulador + nota * pesos[index];
  }, 0);

  const somaPesos = pesos.reduce((acumulador, peso) => {
    return acumulador + peso;
  }, 0);

  return somaProdutos / somaPesos;
}

// Exemplo de utilização
const notas = [7, 8, 9, 6, 7];
const pesos = [1, 2, 2, 1, 1];

try {
  const mediaPonderada = calcularMediaPonderada(notas, pesos);
  console.log(`A média ponderada é: ${mediaPonderada.toFixed(2)}`);
} catch (error) {
  console.error(error.message);
}
