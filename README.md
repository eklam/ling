Requirements
	The language must run on Unix Based, Windows, JVM and Browsers

Goals
	Be clear and simple
	Remove all unnecessary and boilerplate code

Other details
	All functions work like extension method where "this" is the first argument

Built-In Types

Object Type

	object foo
	bar = {}
	object? nullFoo
	nullBar = null

Plain Type

	Usage:

		plain plainRecord
			type      [02]int
			name      [50]char
			docNumber [11]char
			userType  [05]int

		plainRecord = "02Renan                                             3237958980100001"

		int type = plainRecord.type
		string name = plainRecord.name
		string docNumber = plainRecord.docNumber
		userType = plainRecord.userType

		plainRecord.type = 48
		plainRecord.name = "Neias"

		// plainRecord now contains "48Neias                                             3237958980100001"

Numeric Types

	abstract number

		All numbuer variable default value is 0

	Integer Types

		byte : number // 1 byte
		short : byte // 2 byte
		int : short // 4 byte
		long : int // 8 bytes

	Float Types

		float : number // 4 bytes
		double : float // 8 bytes

	Decimal Types
	
		decimal : number // 16 bytes

Collections Types

	map

		Usage:



	list

		All list default value is []

		Usage:

			int[] array  // ??????

			array[0] = 0
			array.add(1)
			array[2] = 2

			int[] array2 = [3, 4]
			array2.add(5)
			array2 += 6

			newArray = array + array2 // newArray contains: 0, 1, 2, 3, 4, 5, 6

			firstItem = newArray.dequeue()
			// newArray contains: 1, 2, 3, 4, 5, 6

			lastItem = newArray.pop()
			// newArray contains: 1, 2, 3, 4, 5

			lastItem = newArray.pop()
			// newArray contains: 1, 2, 3, 4

			map[int, string] dePara 

			dePara.add(1, 'Renan')
			dePara[2, 'Leo']
			dePara.add(3, 'adnilson')

			dePara2 = [[5, 'Marcelo'], [6, 'Eduardo']]
			dePara2.add(7, 'hdhdjt')

			novoDePara = dePara + dePara2
			renan = novoDePara[1]
			leo = novoDePara[2]

String Types

	char 

	Char default value is ' '

	string : char[]

	String keyword is the same thing as char[]. Both are the same type

	List methods:

		trim:itemToTrim=default

			Example:

				array = [0, 1, 2, 3, 4, 0]
				array = array.trim // now array contains [1, 2, 3, 4]

				name = " renan "
				name = name.trim // now name contains "renan"

				surname = "- malke -"
				surname = surname.trim('-') // now surname contains " malke "

				lastname = "- stigliani -"
				lastname = surname.trim("- ") // now surname contains "stigliani"

		triml:itemToTrim=default

			Example:

				array = [0, 1, 2, 3, 4, 0]
				array = array.trim // now array contains [1, 2, 3, 4, 0]

				name = " renan "
				name = name.trim // now name contains "renan "

				surname = "- malke -"
				surname = surname.trim('-') // now surname contains " malke -"

				lastname = "- stigliani -"
				lastname = surname.trim("- ") // now surname contains "stigliani -"

		trimr:itemToTrim=default

			Example:

				array = [0, 1, 2, 3, 4, 0]
				array = array.trim // now array contains [0, 1, 2, 3, 4]

				name = " renan "
				name = name.trim // now name contains " renan"

				surname = "- malke -"
				surname = surname.trim('-') // now surname contains "- malke "

				lastname = "- stigliani -"
				lastname = surname.trim("- ") // now surname contains "- stigliani"

		length

			Example:

				array = [0, 1, 2, 3, 4, 0]
				len = array.length // len holds 6

				name = " renan "
				name = name.trim.length // len holds 5

		left:count

			Example:

				array = [0, 1, 2, 3, 4, 0]
				array = array.left(3) // now array contains [0, 1, 2]

		rigth:count

			Example:

				name = " renan "
				name = name.trim.rigth(3) // name holds "nan"

		sub:start=0, end

			array = [0, 1, 2, 3, 4, 0]
			array = array.sub(2, 4) // now array contains [2, 3]

			name = " renan "
			name = name.sub(4) // now name contains " ren"

		remove:itemToRemove

			array = [0, 1, 2, 3, 4, 0]
			array = array.remove(2) // now array contains [0, 1, 3, 4, 0]
			array = array.remove(0, 1) // now array contains [3, 4]

			name = " renan "
			name = name.remove(" e") // now name contains "rnan"

		concact:separator, listToJoin

			array = [0, 1, 2]
			array = array.concact([3, 4, 5]) // array containt [0, 1, 2, 3, 4, 5]

			name = "renan"
			lastName = "stigliani"

			fullName = name.concact(' ', lastName) // name constaint "renan stigliani"

