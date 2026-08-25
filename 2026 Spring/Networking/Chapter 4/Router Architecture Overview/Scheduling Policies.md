Priority scheduling: 
	Arriving traffic classified, queued by class
		Any header field can be used for classification
Round Robin:
	Arriving traffic classified, queued by class
		Any header field can be used for classification
Weighted Fair Queuing (WFQ):
	Generalized Round Robin
		W(red) = 2
		W(green) = 1
		W(blue) = 1
		Red -> Red -> Green -> Blue
		W(red) = 0.5
		W(green) = 0.25
		W(blue) = 0.25
			W(red) = W(red) / W(i) = 2 / 1 + 1 + 2 = 2 / 4 = 50%
	5 *  Service Time (3) = 15 units
