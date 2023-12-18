import dash
import dash_html_components as html


#it is interesting to note that dash follows flask pattern

#__name__ locates static assets
app = dash.Dash(__name__)

#main subject
app.layout = html.Div()


#callback -- interactivity
@app.callback()

app.run_server()


