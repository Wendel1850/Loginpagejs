# Loginpagejs
// Função para verificar as credenciais do usuário
function verificarCredenciais(username, password) {
  // Simula uma requisição ao servidor para verificar as credenciais
  // Substitua por uma requisição real ao seu servidor
  const usuarios = [
    { username: 'admin', password: 'admin' },
    { username: 'user', password: 'user' }
  ];

  const usuario = usuarios.find(u => u.username === username && u.password === password);

  if (usuario) {
    // Redireciona para a página de dashboard
    window.location.href = '/dashboard';
  } else {
    // Exibe uma mensagem de erro
    document.getElementById('erro').innerHTML = 'Usuário ou senha inválidos';
  }
}

// Função para lidar com o envio do formulário de login
function handleSubmit(event) {
  event.preventDefault();
  const username = document.getElementById('username').value;
  const password = document.getElementById('password').value;
  verificarCredenciais(username, password);
}

// Adiciona o evento de submit ao formulário
document.getElementById('form-login').addEventListener('submit', handleSubmit);
