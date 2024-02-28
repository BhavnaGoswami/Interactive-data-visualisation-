from django.urls import path
from charts.views import chart_view

urlpatterns = [
    path('', chart_view, name='chart_view'),
]
