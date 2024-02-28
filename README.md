<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Data Visualization</title>
</head>
<body>
    <h1>Data Visualization</h1>
    <form method="post">
        {% csrf_token %}
        {{ form.as_p }}
        <button type="submit">Submit</button>
    </form>
    <hr>
    <div>
        {{ bar_chart_html|safe }}
    </div>
</body>
</html>
