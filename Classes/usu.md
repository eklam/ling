class Usuario

  string Nome
  string Sobrenome
  date DataNascimento
  [masculino|feminino|outros] Genero // isso eh um auto enum!!!
  Perfil[] Perfis
  
  :Nome, DataNascimento, Sobrenome="", Genero=Genero.outros, Perfis=[]
    if date.today - DataNascimento <= 21
      exception
        "Usuario deve possui pelo menos 21 anos"

  adicionarPerfil:perfil
    Perfis.add(perfil)
