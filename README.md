from django.shortcuts import render
from .forms import DataForm
import plotly.graph_objs as go

def chart_view(request):
    if request.method == 'POST':
        form = DataForm(request.POST)
        if form.is_valid():
            form.save()
    else:
        form = DataForm()

    data = Data.objects.all()
    x = [item.name for item in data]
    y = [item.value for item in data]

    bar_chart = go.Figure(data=[go.Bar(x=x, y=y)])
    bar_chart_html = bar_chart.to_html(full_html=False)

    context = {'form': form, 'bar_chart_html': bar_chart_html}
    return render(request, 'charts/chart.html', context)
