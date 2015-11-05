# Norm
### A js library for normalization/denormalization of objects.

Norm is designed to allow easier denormalization of objects prior to persisting in flat sql tables, as well as normalizing the objects upon retrieval.

	var norm = new Norm();
	
	var obj = {
		a: 'first',
		b: {
			c: 'second'
		}
	};
	
	norm.denormalize(obj);
	
	//produces:
	//
	//{
	//	a: 'first',
	//	b_c: 'second'
	//}
	

Currently, only fixed index arrays (those that always have a set number of items) are supported.

	var norm = new Norm();
	
	var obj = {
		a: 'first',
		b: [
			'second',
			'third'
		]
	};
	
	norm.denormalize(obj);
	
	//produces:
	//
	//{
	//	a: 'first',
	//	b_0: 'second',
	//	b_1: 'third'
	//}
	
