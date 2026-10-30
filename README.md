Практическая работа: Объектно-ориентированное программирование в Dart (Flutter Architecture)

Тема 1. Классы, инкапсуляция, методы и геттеры/сеттеры

<img width="1909" height="1021" alt="1 1" src="https://github.com/user-attachments/assets/3ff314c4-111d-43f5-8aa1-ea7dadd20fa8" />

class Thermostat {
  double _temperatureCelsius;

  Thermostat([this._temperatureCelsius = 0.0]);

  double get temperatureFahrenheit => (_temperatureCelsius * 1.8) + 32;

  double get temperatureCelsius => _temperatureCelsius;

  set temperatureCelsius(double value) {
    if (value >= -50 && value <= 100) {
      _temperatureCelsius = value;
    } else {
      throw ArgumentError('Температура должна быть в диапазоне от -50 до +100 °C');
    }
  }
}

void main() {
  var term = Thermostat(25.0);
  
  print('${term.temperatureCelsius}°C = ${term.temperatureFahrenheit}°F'); 

  term.temperatureCelsius = -10;
  print('${term.temperatureCelsius}°C = ${term.temperatureFahrenheit}°F'); 
}
