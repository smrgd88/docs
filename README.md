AJAX으로 API에 file 보내기

	function sendFile(){
		var data = new FormData();
		data.append('file', YOUR_FILE_OBJECT);

		$.ajax({
			 type:'POST',
			 crossDomain: true,
			 url:"API-URL",
			 data:data,
			 contentType : false,
			 processData : false,
			 beforeSend:function(xhrObj){
				xhrObj.setRequestHeader("something","important");
	      ...
	      }
		 }).done(function(data) {
				console.log(data);

	    }).fail(function(jqXHR, textStatus, errorThrown) {
		 console.log(jqXHR);
		 console.log(textStatus);
		 console.log(errorThrown);
	    });
	}
