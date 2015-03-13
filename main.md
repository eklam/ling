
Usuario[] lstUser

renan = Usuario("Renan", 1988-11-09, "Malke Stigliani", Genero.masculino)
adriele = Usuario(
            "Adriele"
            1988-03-14
            "Correa"
            Genero.feminino)

lstUser.add(renan)
            
admin = Perfil("Admin")

Acessos[] lstAcessos

homeLeitura = Acesso("homeLeitura")
Acesso homeEscrita = Acesso("homeEscrita")
bookLeitura = Acesso("bookLeitura")
Acesso bookBoletagem = "bookBoletagem"
Acesso distribuicao = "distribuicao" 
confirmation = "confirmation"

lstTemp = [bookLeitura, bookBoletagem]
lstTemp2 = [distribuicao]
lstTemp2.add(confirmation)
   
lstAcessos.add(homeLeitura, homeEscrita, lstTemp)
lstAcessos.add(lstTemp2)

lstAcessos.add("basket")
lstAcessos.add(2) // esse da exception !

admin.Acessos = lstAcessos

perfilMesa = Perfil("Mesa", [homeLeitura, homeEscrita, bookLeitura, bookBoletagem])
perfilMiddle = Perfil("Middle", [homeLeitura, bookLeitura, distribuicao, confirmation])

Perfil[] lstPerfil = [admin, perfilMesa, perfilMiddle]

renan.Perfis = lstPerfil // esta associando
adriele.Perfis = [lstPerfil] // esta criando uma nova lista

lstUser.add(adriele)

lstUser.add(null) // isso da erro de compilacao

Usuario adnilson = null // isso da erro de compilacao

Usuario? leleo = null // isso pode
Usuario? rafael // isso pode e é null tambem

lstUser.add(leleo) // isso da erro de compilacao
lstUser.add(rafael) // isso da erro de compilacao

if leleo
	lstUser.add(leleo) // isso pode

if rafael
	lstUser.add(rafael) // isso pode

acessosAtivos = lstAcessos.filter(:x x.Ativo)
perfisAtivos = lstPerfil.filter(:x x.Acessos.count(:y y.Ativo))

lstUser = lstUser.sort(:x x.DataNascimento).then(:x x.Nome)

renanFound = lstUser.single(:x x.Nome == 'Renan')

renanFound2 = lstUser.single(['Nome', 'Renan'], ['DataNascimento', 'Renan'])

nomes = lstUser.select(:x x.Nome)

numbers_0_to_9 = [0..10]
numbers_0_to_9 = [..10]
numbers_0_to_9 = range(0, 10)
numbers_0_to_9 = range(10)

for i in [..list.length]
	x = list[i]

for x in list
	


allPairs_up_to_10 = [..10].filter(:i i % 2 == 0)



filter:list, function predicate
	for x in list
		if predicate(x)
			yield x

filter:list, conditions
	for x in list
		for cond in conditions
			if !applyCondition(x, cond)
				break
		yield x

single:list
	if list.length == 1
		return list[0]
	exception 
		"More than one value was found"

single:list, function predicate
	return single(filter(list, predicate))

single:lst, conditions
	return single(list, conditions)

first:list, function predicate
	return filter(list, predicate)

first:list, conditions
	return filter(list, conditions)

take:list, long size
	for [x, i] in list
		if i < lenght
			yield x

skip:list, long size
	for [x, i] in list
		if i >= size
			yield x

reverse:list
	length = list.length
	for [x, i] in list
		yield list[length - i]

count:list, function predicate
	list.filter(predicate).length

sort:list, function func
	exception
		"Not implemented yet"

then:list, funcion func