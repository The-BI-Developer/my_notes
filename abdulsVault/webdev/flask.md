flask web framework= WSGI toolkit+ JINJA (dynamic data source)

object of flask class is considered wsgi application

app.route(rule,options) #rule: function <--> url
			#option: params associated with rule object

app.run(host, port, debug, options)  

#app routing used to access specific page

rule = localhost:5000/<whatever>/<whatever>

def home() is a view function

#WEB FRAMEWORKS
All web frameworks obey HTTPS protcol and have following methods for data communication

@app.route('/login',methods = ['<GET/HEAD/POST/PUT/DELETE>']) 

#Request object
attributes = [form,args,cookies,files,methods]

#html forms
<form action="/action_page.php" method="get">
  <label for="fname">First name:</label>
  <input type="text" id="fname" name="fname"><br><br>
  <label for="lname">Last name:</label>
  <input type="text" id="lname" name="lname"><br><br>
  <input type="submit" value="Submit">
</form>

#POSTING AND GETTING DATA

@app.route('/')

#customer.html contains <form action="https://localhost:5000/posting" method="post">

def customer():
    return render_template('customer.html')

#uses % for key,value in jinja_result.items()
app.route('/posting',methods=['POST','GET'])
def show_data():
    if request.method == 'POST':
        result = request.form
        return render_template('result_data.html',jinja_result = result)

#CLIENT-SERVER architecture


#REQUEST OBJECT
1 USING QUERY ARGUMENTS
@app.route('/query-example')
def query_example():
    # if key doesn't exist, returns None
    language = request.args.get('language')

    # if key doesn't exist, returns a 400, bad request error
    framework = request.args['framework']

    # if key doesn't exist, returns None
    website = request.args.get('website')

    return '''
              <h1>The language value is: {}</h1>
              <h1>The framework value is: {}</h1>
              <h1>The website value is: {}'''.format(language, framework, website)

#Equal to http://localhost:5000/language=<>&framework=<>&website=<>
#supplied by caller of the endpoint

2 FORM HANDLING
@app.route('/form-example',methods=['GET','POST'])
def form_example():
    if request.method=="POST":
        lang = request.form.get('lang')
        fw = request.form.get('fw')
        return f'''
            <h1>POST</h1>
            
            <p>Language value is: {lang}</p>
            <p>Framework value is: {fw}</p>
            '''
    else:
        return '''
                <h1>HANDLE THE GET REQUEST</h1>
                <form method="POST">
                    
                    <p><label>Language: <input type="text" name="lang"></label></p>
                    <p><label>Framework: <input type="text" name="fw"></label></p>
                    <input type="submit" value="POST">
                </form>'''

3 DOWNLOADING FILE CODE
from flask import Flask, make_response,request
import pandas as pd

app = Flask(__name__)

@app.route('/')
def open_page():
    return render_template('btn.html')

@app.route('/get_data',methods=['GET','POST'])
def show_data():
    if request.method == 'POST':
        df = pd.DataFrame({"id":[1,2,3],"name":['x','y','z']})
        # Create a response object with the appropriate headers
        resp = make_response(df.to_csv())
        resp.headers["Content-Disposition"] = "attachment; filename=export.csv"
        resp.headers["Content-Type"] = "text/csv"
        return resp
if __name__ == '__main__':
    app.run(debug=True)

#xlsx version
from flask import Flask, make_response,request
import pandas as pd
from io import BytesIO

app = Flask(__name__)

@app.route('/')
def open_page():
    return render_template('btn.html')

@app.route('/get_data',methods=['GET','POST'])
def show_data():
    if request.method == 'POST':
        df = pd.DataFrame({"id":[1,2,3],"name":['x','y','z']})
        output = BytesIO()
        writer = pd.ExcelWriter(output, engine='xlsxwriter')
        df.to_excel(writer)
        writer.close()
        resp = make_response(output.getvalue())
        resp.headers["Content-Disposition"] = "attachment; filename=my_file.xlsx"
        resp.headers["Content-Type"] = "application/vnd.openxmlformats-officedocument.spreadsheetml.sheet"
        return resp

if __name__ == '__main__':
    app.run(debug=True)

