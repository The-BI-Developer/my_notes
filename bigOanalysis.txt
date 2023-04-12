TIMEIT
	timeit.timeit(n [trials], global=gobals [allows for using functions])
	Check XOR algorithm example for swapping numbers
RECOMMENDATION
	make it work --> make it fast

CPROFILE
	efficiency of functions and programs.
	USAGE
		python -m cProfile <file.py> #m means run as script
		cProfile.run('program\/script_to_run')

BIG-O (read as follows - "on the order of ___")
	How code slows as data grows?
	fastest --> slowest: O(1), O(log.n),O(n**2),O(n.log.n),O(n**2),O(2**n),O(n!). Note logs assume base 2!
	CASES
		binary search of alphabetical book order, divide & conquer algorithms - O(log.n)
		duplicates search - O(n**2)
		*sorting into alphabetical order + binary search - O(n.log.n)
		read each book - O(n)
		is it empty? - O(1)
		
*very common as seen in merge, quicksort, heapsort, temsort
	1. Drop coefficients and constants
	2. example: 1 + 2n + 1 = 2n + 2 = n (linear time complexity)
		def readinglist(books):
				total_books = 0 # a step
				for book in books:# n * steps in loop
					print(book) # a step
					total_books += 1 #a step
				print(total_books) #a step
	3. Many nested loops results in n**2, poly time complexity
	
	4. {nested : O(n**2), search: O(n), while loop for binary : O(logn),divide & conquer: {per item:O(nlogn),else:O(logn)},possibilities : {combinations : O(2**n), permutations : O(n!)} }
	

	PRACTICAL STUFF
		cProfile > bigO
		n is data structure as in {n1,n2,n3, ..., n_i-1)



	

					
	
	

		
		
		
	
	
