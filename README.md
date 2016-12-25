<!DOCTYPE html>
<html>
<head>
    <link href="css/bootstrap.min.css" rel="stylesheet" type="text/css" />
    <script src="js/bootstrap.min.js" type="text/javascript"></script>
	
    <title>Simple Quiz</title>
	
	<script>

     //JavaScript Array to store answers
     var answers = new Array();


     //Function to add answer to 'answers' Array
     var addAnswer = function(id,value) {
        
        //Block to check if question's answer is changed
        for(i=0;i<answers.length;i++){

            if(answers[i].id==id)
            {
                answers[i].value = value;
            }
        }

        //Function to push id and value to the 'answers' Array
        answers.push({
                            id: id,
                            value: value
                      });

     }

     //Function to add all the answers to localStorage 'quiz'
     var calculateResult = function() {
       
         //set localStorage 'quiz' to blank if null
         if (window.localStorage.getItem("quiz")==null) {
             window.localStorage.setItem("quiz","");
         }
         else {
             window.localStorage.removeItem("quiz"); //remove localStorage 'quiz' if already present
         }

             window.localStorage.setItem("quiz", JSON.stringify({answers: answers})); //add answers array to localStorage 'quiz'
             window.location.href = "result.html"; //redirect to result page
    }

    </script>

</head>

<body>

	<div id="page" class="container">

		<h1>Quiz</h1>
		
		<form id="quiz" method="get">
		
                    <div class="row">

                    <div class="col-md-4">

                    <h3>QUESTION 1 HERE...</h3>
                    
                    <div>
                        <input class="form-input" type="radio" name="q1" value="A" onchange="addAnswer(this.name,this.value)"/>
                        <label>A) CORRECT ANSWER</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q1" value="B" onchange="addAnswer(this.name,this.value)" />
                        <label>B) OPTION 2</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q1" value="C" onchange="addAnswer(this.name,this.value)" />
                        <label>C) OPTION 3</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q1" value="D" onchange="addAnswer(this.name,this.value)" />
                        <label>D) None of the above</label>
                    </div>
                
                </div>
                
                    <div class="col-md-4">
                
                    <h3>QUESTION 2 HERE...</h3>
                    
                    <div>
                        <input class="form-input" type="radio" name="q2" value="A" onchange="addAnswer(this.name,this.value)" />
                        <label>A) OPTION 1</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q2" value="B" onchange="addAnswer(this.name,this.value)" />
                        <label>B) CORRECT ANSWER</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q2" value="C" onchange="addAnswer(this.name,this.value)" />
                        <label>C) OPTION 2</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q2" value="D" onchange="addAnswer(this.name,this.value)" />
                        <label>D) OPTION 3</label>
                    </div>
                
                    </div>
                
                
                    <div class="col-md-4">
                
                
                    <h3>QUESTION 3 HERE...</h3>
                    
                    <div>
                        <input class="form-input" type="radio" name="q3" value="A" onchange="addAnswer(this.name,this.value)" />
                        <label>A) OPTION 1</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q3" value="B" onchange="addAnswer(this.name,this.value)" />
                        <label>B) OPTION 2</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q3" value="C" onchange="addAnswer(this.name,this.value)" />
                        <label>C) CORRECT ANSWER</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q3" value="D" onchange="addAnswer(this.name,this.value)" />
                        <label>D) OPTION 3</label>
                    </div>
                
                </div>
                
                <div class="col-md-4">
                
                    <h3>QUESTION 4 HERE...</h3>
                    
                    <div>
                        <input class="form-input" type="radio" name="q4" value="A" onchange="addAnswer(this.name,this.value)" />
                        <label>A) OPTION 1</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q4" value="B" onchange="addAnswer(this.name,this.value)" />
                        <label>B) OPTION 2</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q4" value="C" onchange="addAnswer(this.name,this.value)" />
                        <label>C) OPTION 3</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q4" value="D" onchange="addAnswer(this.name,this.value)" />
                        <label>D) CORRECT ANSWER</label>
                    </div>
                
                </div>
                
                <div class="col-md-4">
                
                    <h3>QUESTION 5 HERE...</h3>
                    
                    <div>
                        <input class="form-input" type="radio" name="q5" value="A" onchange="addAnswer(this.name,this.value)" />
                        <label>A) CORRECT ANSWER</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q5" value="B" onchange="addAnswer(this.name,this.value)" />
                        <label>B) OPTION 1</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q5" value="C" onchange="addAnswer(this.name,this.value)" />
                        <label>C) OPTION 2</label>
                    </div>
                    
                    <div>
                        <input class="form-input" type="radio" name="q5" value="D" />
                        <label>D) OPTION 3</label>
                    </div>
                
                </div>
            
                    </div>
            
            <div class="row">
                <div class="col-md-12">
                    <br>
                    <input type="button" class="btn btn-default" onclick="calculateResult()" class="form-input" value="Calculate" />
                </div>
		
		</form>
	
	</div>
</body>
</html>
