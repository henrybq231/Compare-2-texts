text_1 = "toi mua me con bo con cua con ban toi"

text_2 = "toi mua con con bo me cua con ban than toi"

library = {}

def compare_text(text_input):
	text_input = text_input.split()


	unique = []

	def unique_word(text_input):
		for i in range(0, len(text_input) - 1):
			if text_input[i] not in unique:
				unique.append(text_input[i])
		return unique

	unique = unique_word(text_input)

	print unique

	def compare_lib(unique):
		total = 0
		for i in range(0, len(unique)-1):
			if unique[i] not in library.itervalues():
				library[len(library)+1] = unique[i]
			else:
				total += 1
		rate = total/len(unique)
		if total > 0.65:
			print "This article is supposed to be an duplicate from our source"
		else:
			print "This article is unique"
		return total

	return unique_word(text_input), compare_lib(unique)


compare_text(text_1)
compare_text(text_2)
print library
