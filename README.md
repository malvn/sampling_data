# sampling_data
pip install csvkit  # menginstall package csvkit
python -m pip install sample-stream # menginstall package sample
wget https://github.com/labusiam/dataset/raw/main/weather_data.xlsx # mendownload file xlsx dari website tertera
in2csv weather_data.xlsx --sheet "weather_2014" > weather_2014.csv  # mengekstrak sheet weather_2014 dari file weather_data kemudian dijadikan file weather_2014.csv
in2csv weather_data.xlsx --sheet "weather_2015" > weather_2015.csv  # mengekstrak sheet weather_2015 dari file weather_data kemudian dijadikan file weather_2015.csv
csvstack weather_2014.csv weather_2015.csv > weather.csv  # menggabungkan file weather_2014.csv dan weather_2015.csv menjadi file weather.csv
rm weather_data.xlsx  # menghapus file weather_data.xlsx
cat weather.csv | sample -r 0.3 > sample_weather.csv  # mengambil sample acak 30% dari file weather.csv dan dijadikan file sample_weather.csv
