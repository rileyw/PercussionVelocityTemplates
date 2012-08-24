#macro(getnavtitle $node)
	#if($node.hasProperty("rx:navtitle"))
		#set($titlecandidate = $node.getProperty("rx:navtitle").String)
		#if($titlecandidate.trim().length() > 0)
			#set($title = $titlecandidate)
		#else
			#getcontenttitle($node)
		#end
	#else
		#getcontenttitle($node)
	#end
#end