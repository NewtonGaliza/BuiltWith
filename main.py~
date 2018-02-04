from flask import Flask, render_template, request, url_for, redirect
import builtwith

app = Flask(__name__)

@app.route('/')
def index():
     return render_template('index.html')

@app.route('/builtwith', methods=['GET', 'POST'])
def listar():
    try:
        if request.method == 'POST':
            url = request.form.get(('site'))
        bw = builtwith.parse(url)
        return render_template('list.html', url=url, bw=bw)
    except e:
        internal_server_error(e)
    

@app.errorhandler(500)
def internal_server_error(e):
    return render_template('500.html')



         
if __name__ == '__main__':
    app.run()

