# Bộ kit thực hành MKE-K99 MakerEDU Starter Kit for Arduino

## Giới thiệu

**Bộ kit thực hành MKE-K99 MakerEDU Starter Kit for Arduino** là bộ học tập Arduino được thiết kế dành cho **người mới bắt đầu, học sinh, sinh viên và những người yêu thích điện tử – lập trình – STEM**, giúp biến các kiến thức lý thuyết về vi điều khiển thành những bài thực hành trực quan và dễ tiếp cận. Với **VIETDUINO UNO** làm bộ điều khiển trung tâm, kết hợp cùng **MKE-B03 VIETDUINO IO SHIELD** và hệ thống các module Led, còi buzzer, nút nhấn, biến trở, cảm biến ánh sáng, cảm biến âm thanh, LCD1602 và cảm biến nhiệt độ – độ ẩm, bộ kit cung cấp một hệ sinh thái phần cứng nhỏ gọn để người học từng bước khám phá các nội dung thực hành:

- Hiểu cấu trúc cơ bản của một hệ thống phần cứng Arduino.
- Làm quen với Arduino IDE.
- Viết chương trình Arduino cơ bản.
- Phân biệt tín hiệu **Digital** và **Analog**.
- Sử dụng `digitalRead()` và `digitalWrite()`.
- Sử dụng `analogRead()`.
- Làm quen với **PWM** và `analogWrite()`.
- Sử dụng Serial Monitor và Serial Plotter.
- Làm việc với thư viện Arduino.
- Hiểu nguyên lý giao tiếp **I2C**.
- Đọc dữ liệu từ cảm biến.
- Hiển thị dữ liệu lên LCD1602.
- Kết hợp nhiều cảm biến để tạo các ứng dụng thực tế.

**Bộ kit thực hành MKE-K99 MakerEDU Starter Kit for Arduino** là một **nền tảng thực hành** giúp người học từng bước hình thành tư duy lập trình phần cứng: **Kết nối → Lập trình → Quan sát → Thử nghiệm → Điều chỉnh → Sáng tạo**. Từ những bài học đầu tiên với một chiếc LED, người học có thể tiếp tục kết hợp các module để xây dựng những mô hình thực tế như **đèn tự động theo ánh sáng, đèn phản ứng với âm thanh, thiết bị hiển thị thông tin môi trường** và nhiều dự án Arduino sáng tạo khác.

## Thành phần bộ kit

| STT | Module | Số lượng | Loại |
|---:|---|---:|---|
| 1 | VIETDUINO UNO (Arduino Uno Compatible) | 1 | Bộ điều khiển |
| 2 | MKE-B03 VIETDUINO IO SHIELD | 1 | Shield kết nối |
| 3 | MKE-M01 1-LED 10MM RGYBW MODULE | 1 | Output |
| 4 | MKE-M03 BUZZER MODULE | 1 | Output |
| 5 | MKE-M02 BUTTON RGYBW MODULE | 1 | Input |
| 6 | MKE-M04 POTENTIOMETER RGYBW MODULE | 1 | Analog Input |
| 7 | MKE-S02 LDR LIGHT SENSOR | 1 | Analog Sensor |
| 8 | MKE-S06 SOUND SENSOR | 1 | Analog Sensor |
| 9 | MKE-M07 LCD1602 I2C MODULE | 1 | Display |
| 10 | MKE-S14 DHT11 TEMPERATURE HUMIDITY SENSOR | 1 | Digital Sensor |

## Hướng dẫn sử dụng Vietduino Uno với phần mềm Arduino

### Bước 1: Cài đặt Arduino IDE
- Tải và cài đặt [Phần mềm Arduino IDE từ trang chủ Arduino](https://www.arduino.cc/en/software) phù hợp với hệ điều hành đang sử dụng.

### Bước 2: Kết nối mạch với máy tính
- Kết nối Vietduino Uno với máy tính bằng cáp USB-C.
- Khi kết nối thành công, LED nguồn (ON) trên mạch sẽ sáng.

### Bước 3: Cài đặt driver CH340
- Vietduino Uno sử dụng IC CH340 để giao tiếp USB–UART.
- Thông thường Driver sẽ tự nhận trên hầu hết các hệ điều hành, nếu máy tính chưa nhận driver, [tải và cài đặt Driver CH343P tại đây.](https://www.wch-ic.com/downloads/CH341SER_ZIP.html)

### Bước 4: Cấu hình mạch trong Arduino IDE
Thực hiện các thiết lập sau trong Arduino IDE:
- Chọn loại board: Tools → Board → Arduino AVR Boards → Arduino Uno
- Chọn cổng kết nối (Port): Tools → Port → chọn cổng tương ứng với Vietduino Uno (nếu chưa xác định được, hãy rút cáp USB và cắm lại để nhận diện cổng mới xuất hiện)
![Vietduino Uno](/extras/VietduinoUno3.jpg)

### Bước 5: Nạp chương trình thử nghiệm (Hello Word!)
Sau khi cấu hình xong, bạn có thể nạp chương trình "Hello Word!" để kiểm tra mạch.
Chương trình này sẽ hiển thị ký tự "Hello Word!" lên Serial Monitor của phần mềm Arduino
```ino
/*
  Hello World!
  Gửi thông báo "Hello World!" đến Serial Monitor thông qua cổng Serial của VIETDUINO UNO.
*/

void setup() {
  // Khởi tạo giao tiếp Serial với tốc độ 9600 baud
  Serial.begin(9600);

  // Gửi thông báo khởi động
  Serial.println("Start!");
}

void loop() {
  // Gửi "Hello World!" mỗi 1 giây
  Serial.println("Hello World!");
  delay(1000);
}
```

### Bước 6: Cài đặt bộ thư viện MKE-ONE trên phần mềm Arduino
Tại giao diện chính của phần mềm Arduino:
- Trong **Tools / Library Manager**, tìm và cài đặt bộ thư viện tổng hợp **"MKE_ONE" by MakerEdu.vn**
- Các chương trình mẫu trong mỗi bài học sẽ có tại tại **File / Examples / MKE_ONE / Kit / MKE-K99 MakerEDU Starter Kit for Arduino**
- Nạp chương trình, sau đó kết nối các phần cứng theo hướng dẫn trong mỗi bài học.
- Xem kết quả mạch hoạt động theo chương trình đã nạp.

## Hướng dẫn kết nối Vietduino Uno với MKE-B03 Vietduino IO Shield

Mạch đế kết nối MKE-B03 Vietduino IO Shield là bo mở rộng chân chuyên dụng cho các Vietduino Uno, được phát triển bởi MakerEDU nhằm giúp việc kết nối cảm biến và module chức năng trở nên nhanh chóng, trực quan và an toàn hơn. Mạch sử dụng chuẩn kết nối rào đực 2.54 mm (0.1″ male header) linh hoạt với bố trí màu sắc rõ ràng:

- Vàng, Xanh Lá: chân tín hiệu
- Đỏ: Chân nguồn dương
- Đen: Chân nguồn âm

MKE-B03 Vietduino IO Shield giúp người dùng dễ dàng đấu nối mà không lo nhầm cực khi triển khai các dự án học tập STEM, IoT hoặc robot. Toàn bộ các chân GPIO của mạch Vietduino Uno được đưa ra đầy đủ kèm theo cặp nguồn 5V – GND, giúp cấp nguồn trực tiếp cho cảm biến và module ngoại vi. Ngoài ra, mạch còn tích hợp nhiều cổng I2C với chuẩn màu riêng biệt (GND - Đen, 5V- Đỏ, SDA - Vàng, SCL - Xanh Lá), thuận tiện cho việc mở rộng hệ thống với các module, cảm biến giao tiếp I2C.

**Kết nối mạch như hình, khi đó phần chân IO trên Shield ký hiệu AR (Arduino) chính là các chân tín hiệu của Vietduino Uno:**
![Vietduino Uno](/extras/VietduinoUno4.jpg)

# Các bài thực hành

## Bài 1 – Điều khiển LED bằng tín hiệu Digital

Chúng ta sẽ bắt đầu làm quen với việc điều khiển phần cứng Arduino thông qua bài học đầu tiên: **điều khiển LED**.

Trong một hệ thống điều khiển cơ bản có ba thành phần chính:

- **Input (Đầu vào):** nhận tín hiệu từ nút nhấn, cảm biến...
- **Control (Điều khiển):** xử lý tín hiệu và đưa ra quyết định.
- **Output (Đầu ra):** thực hiện hành động như bật LED, phát âm thanh...

Trong bài học này, **VIETDUINO UNO** đóng vai trò là bộ điều khiển và **MKE-M01 1-LED 10MM RGYBW MODULE** là thiết bị đầu ra.

### Tín hiệu Digital là gì?

**Digital Signal (tín hiệu số)** là tín hiệu có các trạng thái xác định. Với Arduino UNO, tín hiệu Digital cơ bản gồm hai trạng thái:

| Trạng thái | Giá trị | Mức điện áp |
|:---:|:---:|:---:|
| `LOW` | `0` | 0V |
| `HIGH` | `1` | 5V |

Khi Arduino xuất tín hiệu `HIGH` đến chân điều khiển LED, LED sẽ bật. Khi xuất tín hiệu `LOW`, LED sẽ tắt.

### Kết nối

Kết nối **MKE-M01 1-LED 10MM RGYBW MODULE** với **MKE-B03 VIETDUINO IO SHIELD** như sau:

| VIETDUINO UNO + IO SHIELD | MKE-M01 | Chức năng |
|:---:|:---:|:---|
| `EX-5V` | `+` | Nguồn dương 5VDC |
| `GND` | `-` | Nguồn âm 0VDC |
| `AR-4` | `S` | Tín hiệu Digital |

> **Lưu ý:** Chân tín hiệu `S` của MKE-M01 được kết nối với **Digital Pin D4** của VIETDUINO UNO.

### Chương trình

Nạp chương trình sau vào **VIETDUINO UNO**:

```ino
// Lesson 1: Digital Output - LED Blink

int ledPin = 4;

void setup() {
  pinMode(ledPin, OUTPUT);
}

void loop() {
  digitalWrite(ledPin, HIGH);
  delay(1000);

  digitalWrite(ledPin, LOW);
  delay(1000);
}
```

### Kết quả

Sau khi chương trình được nạp thành công, **MKE-M01 LED Module** sẽ hoạt động theo chu kỳ:

```text
LED sáng
   ↓
Chờ 1 giây
   ↓
LED tắt
   ↓
Chờ 1 giây
   ↓
Lặp lại
```

**Kết quả thực tế:** LED sẽ **sáng trong 1 giây, tắt trong 1 giây và lặp lại liên tục**.

### Phân tích chương trình

#### 1. Khai báo biến `ledPin`

```ino
int ledPin = 4;
```

Dòng lệnh này khai báo một biến có kiểu dữ liệu `int` với tên `ledPin` và giá trị `4`, điều này cho biết LED được điều khiển thông qua **Digital Pin D4**.

Việc sử dụng biến `ledPin` giúp chương trình dễ đọc và thuận tiện thay đổi chân điều khiển khi cần thiết.

Ví dụ, nếu muốn chuyển LED sang chân D7, chỉ cần thay đổi:

```ino
int ledPin = 7;
```

#### 2. Hàm `setup()`

```ino
void setup() {
  pinMode(ledPin, OUTPUT);
}
```

Hàm `setup()` được thực thi **một lần duy nhất** khi Arduino được cấp nguồn hoặc reset. Trong bài học này, hàm `setup()` được sử dụng để thiết lập chân D4 làm **ngõ ra (OUTPUT)**.

```ino
pinMode(ledPin, OUTPUT);
```
Lệnh `pinMode()` cấu hình chế độ hoạt động của một chân Digital là INPUT hoặc OUTPUT, trong đó:
- `pin`: số chân cần thiết lập.
- `mode`: chế độ hoạt động của chân.

Vì `ledPin` có giá trị `4`, câu lệnh:

```ino
pinMode(ledPin, OUTPUT);
```
tương đương:
```ino
pinMode(4, OUTPUT);
```
Arduino sẽ sử dụng chân **D4** để xuất tín hiệu điều khiển LED.

#### 3. Hàm `loop()`

```ino
void loop() {
  digitalWrite(ledPin, HIGH);
  delay(1000);

  digitalWrite(ledPin, LOW);
  delay(1000);
}
```

Sau khi hàm `setup()` hoàn thành, Arduino sẽ liên tục thực hiện các lệnh bên trong hàm `loop()`.

Trong chương trình này, `loop()` thực hiện theo trình tự:

```text
Bật LED → Chờ 1 giây → Tắt LED → Chờ 1 giây → Quay lại đầu loop()
```

Do `loop()` được lặp liên tục nên LED sẽ nhấp nháy không ngừng.

#### 4. Bật / tắt LED bằng `digitalWrite()`

```ino
digitalWrite(pin, value);
```

Hàm `digitalWrite()` được sử dụng để đưa tín hiệu `HIGH` hoặc `LOW` đến một chân Digital, trong đó:
- `pin`: chân Digital cần điều khiển.
- `value`: `HIGH` hoặc `LOW`.

**Khi thực hiện:**

```cpp
digitalWrite(ledPin, HIGH);
```

Arduino đưa chân **D4** lên mức logic `HIGH`.

Kết quả:

```text
D4 = HIGH
↓
Mức điện áp cao
↓
LED sáng
```
**Khi thực hiện:**

```cpp
digitalWrite(ledPin, LOW);
```

Arduino đưa chân **D4** lên mức logic `LOW`.

Kết quả:

```text
D4 = LOW
↓
Mức điện áp thấp
↓
LED tắt
```

#### 5. Tạo thời gian chờ bằng `delay()`

```ino
delay(ms);
```

Hàm `delay()` tạm dừng chương trình trong khoảng thời gian được chỉ định, tính bằng **mili giây (ms)**.

Vì vậy:

```ino
delay(1000);
```

có nghĩa là Arduino sẽ chờ **1 giây (1000ms)** trước khi thực hiện lệnh tiếp theo.

Trong chương trình, lệnh này được sử dụng sau khi bật / tắt LED để LED duy trì trạng thái trong 1 giây.

## Bài 2 – Điều khiển Led bằng nút nhấn

## Mục tiêu

Học:

- Digital Input.
- `digitalRead()`.
- `if...else`.

## Kết nối

```text
Button → D6
LED    → D4
```

## Code

```cpp
const int BUTTON_PIN = 6;
const int LED_PIN = 4;

void setup() {
  pinMode(BUTTON_PIN, INPUT);
  pinMode(LED_PIN, OUTPUT);
}

void loop() {
  int buttonState = digitalRead(BUTTON_PIN);

  if (buttonState == HIGH) {
    digitalWrite(LED_PIN, HIGH);
  } else {
    digitalWrite(LED_PIN, LOW);
  }
}
```

## Kết quả

Nhấn Button → LED sáng.

Thả Button → LED tắt.

Cấu hình D6 cho Button và D4 cho LED được giữ theo tài liệu tham khảo. fileciteturn1file2L226-L234

---

# Lesson 3 – Potentiometer điều khiển tốc độ LED

## Mục tiêu

Làm quen với:

- Analog Input.
- ADC.
- `analogRead()`.

## Kết nối

```text
Potentiometer → A0
LED           → D4
```

## Code

```cpp
const int POT_PIN = A0;
const int LED_PIN = 4;

void setup() {
  pinMode(POT_PIN, INPUT);
  pinMode(LED_PIN, OUTPUT);
}

void loop() {
  int value = analogRead(POT_PIN);

  digitalWrite(LED_PIN, HIGH);
  delay(value);

  digitalWrite(LED_PIN, LOW);
  delay(value);
}
```

## Kết quả

Xoay potentiometer:

- Giá trị nhỏ → LED nhấp nháy nhanh.
- Giá trị lớn → LED nhấp nháy chậm.

Tài liệu tham khảo sử dụng A0 cho potentiometer và minh họa việc dùng giá trị `analogRead()` để thay đổi thời gian `delay()`. fileciteturn1file2L236-L298

---

# Lesson 4 – Buzzer

## Mục tiêu

Học cách điều khiển Buzzer bằng tín hiệu xung.

## Kết nối

```text
Buzzer → D5
```

## Code

```cpp
const int BUZZER_PIN = 5;

void setup() {
  pinMode(BUZZER_PIN, OUTPUT);
}

void loop() {
  tone(BUZZER_PIN, 1000);
  delay(500);

  noTone(BUZZER_PIN);
  delay(500);
}
```

## Kết quả

Buzzer phát âm thanh 1 kHz trong 0,5 giây rồi dừng 0,5 giây.

---

# Lesson 5 – Cảm biến ánh sáng

## Mục tiêu

Tạo một đèn tự động bật khi môi trường tối.

## Kết nối

```text
Light Sensor → A6
LED          → D4
```

## Code

```cpp
const int LIGHT_PIN = A6;
const int LED_PIN = 4;

void setup() {
  pinMode(LIGHT_PIN, INPUT);
  pinMode(LED_PIN, OUTPUT);

  Serial.begin(9600);
}

void loop() {
  int lightValue = analogRead(LIGHT_PIN);

  Serial.println(lightValue);

  if (lightValue < 200) {
    digitalWrite(LED_PIN, HIGH);
  } else {
    digitalWrite(LED_PIN, LOW);
  }

  delay(200);
}
```

> Giá trị `200` chỉ là ngưỡng ví dụ. Hãy mở Serial Monitor và điều chỉnh theo môi trường thực tế.

---

# Lesson 6 – Cảm biến âm thanh

## Mục tiêu

Bật LED khi môi trường có âm thanh đủ lớn.

## Kết nối

```text
Sound Sensor → A2
LED          → D4
```

## Code

```cpp
const int SOUND_PIN = A2;
const int LED_PIN = 4;

void setup() {
  pinMode(SOUND_PIN, INPUT);
  pinMode(LED_PIN, OUTPUT);

  Serial.begin(9600);
}

void loop() {
  int soundValue = analogRead(SOUND_PIN);

  Serial.println(soundValue);

  if (soundValue > 400) {
    digitalWrite(LED_PIN, HIGH);
  } else {
    digitalWrite(LED_PIN, LOW);
  }

  delay(50);
}
```

## Quan sát bằng Serial Plotter

Mở:

```text
Tools → Serial Plotter
```

Sau đó tạo tiếng động gần cảm biến.

Giá trị cảm biến sẽ thay đổi theo âm thanh môi trường. Tài liệu tham khảo cũng dùng Serial Plotter để trực quan hóa tín hiệu Sound Sensor. fileciteturn2file0L65-L74

---

# Lesson 7 – LCD1602

## Mục tiêu

Thay thế bài OLED trong tài liệu tham khảo bằng LCD1602 để học:

- LCD ký tự.
- I2C.
- Arduino Library.
- Hiển thị dữ liệu.

Tài liệu tham khảo sử dụng OLED để minh họa việc cài thư viện và hiển thị `"Hello World!"`; bài học MakerEDU chuyển phần này sang LCD1602. fileciteturn1file4L413-L469

## Kết nối

LCD1602 I2C sử dụng:

```text
VCC → 5V
GND → GND
SDA → SDA
SCL → SCL
```

Trên Arduino UNO:

```text
SDA = A4
SCL = A5
```

## Cài thư viện

Trong Arduino IDE:

```text
Sketch
  → Include Library
    → Manage Libraries
```

Tìm:

```text
LiquidCrystal I2C
```

Cài một thư viện LiquidCrystal I2C tương thích với board.

## Code Hello MakerEDU

```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>

#define LCD_ADDRESS 0x27

LiquidCrystal_I2C lcd(LCD_ADDRESS, 16, 2);

void setup() {
  lcd.init();
  lcd.backlight();

  lcd.setCursor(0, 0);
  lcd.print("Hello MakerEDU!");

  lcd.setCursor(0, 1);
  lcd.print("Arduino Starter");
}

void loop() {
}
```

## Nếu LCD không hiển thị

Thử:

```cpp
#define LCD_ADDRESS 0x3F
```

Nếu vẫn không hiển thị, sử dụng I2C Scanner để xác định địa chỉ thực tế.

### I2C Scanner

```cpp
#include <Wire.h>

void setup() {
  Wire.begin();
  Serial.begin(9600);

  Serial.println("I2C Scanner");
}

void loop() {
  byte error;
  byte address;

  int devices = 0;

  for (address = 1; address < 127; address++) {
    Wire.beginTransmission(address);
    error = Wire.endTransmission();

    if (error == 0) {
      Serial.print("I2C device found at 0x");
      if (address < 16) {
        Serial.print("0");
      }
      Serial.println(address, HEX);
      devices++;
    }
  }

  if (devices == 0) {
    Serial.println("No I2C devices found.");
  }

  delay(3000);
}
```

---

# Lesson 8 – Nhiệt độ và độ ẩm

## Mục tiêu

Đọc nhiệt độ và độ ẩm, sau đó hiển thị lên LCD1602.

## Kết nối

```text
Temperature & Humidity Sensor → D3
LCD1602                       → I2C
```

Tài liệu tham khảo dùng D3 cho cảm biến nhiệt độ/độ ẩm và I2C cho OLED. fileciteturn3file1L264-L283

---

## 8.1 Trường hợp DHT11

### Cài thư viện

Cài thư viện:

```text
DHT sensor library
```

### Code

```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include "DHT.h"

#define DHT_PIN 3
#define DHT_TYPE DHT11
#define LCD_ADDRESS 0x27

DHT dht(DHT_PIN, DHT_TYPE);
LiquidCrystal_I2C lcd(LCD_ADDRESS, 16, 2);

void setup() {
  Serial.begin(9600);

  dht.begin();

  lcd.init();
  lcd.backlight();
  lcd.clear();
}

void loop() {
  float temperature = dht.readTemperature();
  float humidity = dht.readHumidity();

  if (isnan(temperature) || isnan(humidity)) {
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print("Sensor Error");
    delay(1000);
    return;
  }

  lcd.setCursor(0, 0);
  lcd.print("Temp: ");
  lcd.print(temperature, 1);
  lcd.print((char)223);
  lcd.print("C   ");

  lcd.setCursor(0, 1);
  lcd.print("Humi: ");
  lcd.print(humidity, 1);
  lcd.print("%   ");

  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.print(" C, Humidity: ");
  Serial.print(humidity);
  Serial.println(" %");

  delay(1000);
}
```

---

## 8.2 Trường hợp DHT20

Một số phiên bản sử dụng DHT20 thay cho DHT11. Tài liệu tham khảo xác nhận DHT20 được dùng ở các phiên bản mới. fileciteturn3file1L281-L283

Sử dụng đúng thư viện DHT20/Grove Temperature & Humidity Sensor tương ứng với module thực tế.

> **Quan trọng:** Không dùng code DHT11 cho module DHT20. Hãy kiểm tra linh kiện thực tế trước khi chọn chương trình.

---

# Lesson 9 – Áp suất khí quyển

## Mục tiêu

Đọc:

- Áp suất khí quyển.
- Nhiệt độ.
- Độ cao ước tính.

Tài liệu tham khảo mô tả Air Pressure Sensor có thể đo nhiệt độ, áp suất và tính độ cao dựa trên sự thay đổi áp suất theo độ cao. fileciteturn3file1L428-L430

---

## 9.1 BMP280

Với phiên bản sử dụng BMP280, cài thư viện:

```text
Grove BMP280
```

Ví dụ cơ bản:

```cpp
#include <Wire.h>
#include "Seeed_BMP280.h"

BMP280 bmp280;

void setup() {
  Serial.begin(9600);

  if (!bmp280.init()) {
    Serial.println("BMP280 not connected!");
    while (1);
  }
}

void loop() {
  float pressure = bmp280.getPressure();

  Serial.print("Temperature: ");
  Serial.print(bmp280.getTemperature());
  Serial.println(" C");

  Serial.print("Pressure: ");
  Serial.print(pressure);
  Serial.println(" Pa");

  Serial.print("Altitude: ");
  Serial.print(bmp280.calcAltitude(pressure));
  Serial.println(" m");

  Serial.println();

  delay(1000);
}
```

Cấu trúc chương trình BMP280 trong tài liệu tham khảo cũng sử dụng `getTemperature()`, `getPressure()` và `calcAltitude()`. fileciteturn1file8L748-L785

---

## 9.2 SPA06-003 / SPL07-003

Với phiên bản cảm biến áp suất mới, tài liệu tham khảo hướng dẫn sử dụng thư viện:

https://github.com/Seeed-Studio/Seeed_Arduino_SPA06

Thư viện cung cấp chức năng đọc:

- Pressure.
- Temperature.
- Altitude.

Tài liệu tham khảo sử dụng cấu hình đo áp suất 4 Hz, 32 samples và nhiệt độ 4 Hz, 1 sample. fileciteturn1file3L311-L317

Ví dụ:

```cpp
#include <Wire.h>
#include "SPL07-003.h"

#define SPL07_ADDR SPL07_ADDR_DEF

SPL07_003 spl;

void setup() {
  Serial.begin(115200);

  Wire.begin();

  if (!spl.begin(SPL07_ADDR, &Wire)) {
    Serial.println("Error initializing pressure sensor!");
    while (1);
  }

  spl.setPressureConfig(SPL07_4HZ, SPL07_32SAMPLES);
  spl.setTemperatureConfig(SPL07_4HZ, SPL07_1SAMPLE);
  spl.setMode(SPL07_CONT_PRES_TEMP);
}

void loop() {
  if (spl.pressureAvailable() || spl.temperatureAvailable()) {

    double pressure = spl.readPressure();
    double temperature = spl.readTemperature();
    double altitude = spl.calcAltitude();

    Serial.print("Pressure: ");
    Serial.print(pressure, 3);
    Serial.print(" Pa, Temperature: ");
    Serial.print(temperature, 3);
    Serial.print(" C, Altitude: ");
    Serial.print(altitude, 3);
    Serial.println(" m");
  }
}
```

---

# 8. Bonus Projects

# Project 1 – Music Dynamic Rhythm Lamp

## Mô tả

Kết hợp:

- Buzzer.
- LED.

Buzzer phát một giai điệu trong khi LED nhấp nháy theo nhịp.

Đây là project được chuyển từ tài liệu tham khảo và không phụ thuộc vào OLED hoặc accelerometer. fileciteturn3file2L835-L848

## Kết nối

```text
LED    → D4
Buzzer → D5
```

## Code

```cpp
const int BUZZER_PIN = 5;
const int LED_PIN = 4;

int melody[] = {
  262, 294, 330, 349,
  392, 440, 494, 523
};

int duration[] = {
  300, 300, 300, 300,
  300, 300, 300, 600
};

void setup() {
  pinMode(BUZZER_PIN, OUTPUT);
  pinMode(LED_PIN, OUTPUT);
}

void loop() {
  int notes = sizeof(melody) / sizeof(melody[0]);

  for (int i = 0; i < notes; i++) {
    tone(BUZZER_PIN, melody[i]);

    digitalWrite(LED_PIN, HIGH);
    delay(duration[i] * 0.8);

    digitalWrite(LED_PIN, LOW);
    noTone(BUZZER_PIN);

    delay(duration[i] * 0.2);
  }

  delay(2000);
}
```

---

# Project 2 – Intelligent Sound-Light Desk Lamp

## Mô tả

Kết hợp:

- Light Sensor.
- Sound Sensor.
- LED.

LED sẽ bật khi:

- Môi trường tối; **hoặc**
- Có âm thanh vượt ngưỡng.

Project này được giữ theo ý tưởng của tài liệu tham khảo. fileciteturn3file2L1005-L1017

## Kết nối

```text
LED          → D4
Light Sensor → A6
Sound Sensor → A2
```

## Code

```cpp
const int LED_PIN = 4;
const int LIGHT_PIN = A6;
const int SOUND_PIN = A2;

void setup() {
  pinMode(LED_PIN, OUTPUT);
  pinMode(LIGHT_PIN, INPUT);
  pinMode(SOUND_PIN, INPUT);

  Serial.begin(9600);
}

void loop() {
  int lightValue = analogRead(LIGHT_PIN);
  int soundValue = analogRead(SOUND_PIN);

  Serial.print("Light: ");
  Serial.print(lightValue);

  Serial.print(" | Sound: ");
  Serial.println(soundValue);

  if (soundValue > 500 || lightValue < 200) {
    digitalWrite(LED_PIN, HIGH);
  } else {
    digitalWrite(LED_PIN, LOW);
  }

  delay(100);
}
```

Các ngưỡng `500` và `200` là giá trị ví dụ từ project tham khảo; nên hiệu chỉnh lại theo cảm biến và môi trường thực tế. fileciteturn3file2L1030-L1076

---

# Project 3 – Environmental Monitor với LCD1602

Đây là project mở rộng dành riêng cho phiên bản MakerEDU.

## Mục tiêu

Đọc:

- Nhiệt độ.
- Độ ẩm.

và hiển thị trực tiếp trên LCD1602.

## Gợi ý giao diện

```text
Temp: 28.5 C
Humi: 65.2 %
```

Có thể mở rộng bằng Button để chuyển giữa:

```text
Screen 1 → Temperature / Humidity
Screen 2 → Air Pressure
Screen 3 → Light / Sound
```

Project này giúp người học kết hợp:

```text
Sensor
   ↓
Arduino
   ↓
Data Processing
   ↓
LCD1602
```

---

# 9. Tách module khỏi PCB

Nếu phiên bản MakerEDU sử dụng PCB liên kết module, các module có thể được tách ra để sử dụng độc lập.

## Cách thực hiện

1. Ngắt nguồn USB.
2. Xác định các điểm nối giữa module và PCB chính.
3. Dùng kìm cắt PCB hoặc dụng cụ phù hợp để tách module.
4. Làm sạch phần PCB còn dư.
5. Kiểm tra không có chập mạch.
6. Sử dụng Grove Cable để kết nối module với board.

Tài liệu tham khảo cũng mô tả việc tách module bằng các điểm stamp hole và cảnh báo cần thao tác cẩn thận để tránh làm hỏng mạch. fileciteturn3file2L1104-L1120

> **CẢNH BÁO:** Không cắt khi board đang được cấp nguồn.

---

# 10. Khắc phục sự cố

## Arduino IDE không nhận board

Kiểm tra:

- USB cable.
- USB port.
- Driver USB-to-Serial.
- Board đã được chọn đúng chưa.
- Port đã chọn đúng chưa.

Nếu hệ thống sử dụng USB-UART CP2102, cần cài đúng driver cho hệ điều hành. Đây cũng là quy trình được nêu trong tài liệu tham khảo. fileciteturn3file0L149-L157

---

## LCD1602 sáng nền nhưng không có chữ

Kiểm tra:

1. Địa chỉ I2C.
2. Dây SDA/SCL.
3. Biến trở tương phản trên module LCD.
4. Nguồn 5V/GND.
5. Thư viện `LiquidCrystal_I2C`.

Thử:

```cpp
#define LCD_ADDRESS 0x27
```

hoặc:

```cpp
#define LCD_ADDRESS 0x3F
```

Nếu chưa được, chạy I2C Scanner.

---

## LCD không tìm thấy thiết bị I2C

Kiểm tra:

```text
SDA
SCL
VCC
GND
```

Trên Arduino UNO:

```text
SDA → A4
SCL → A5
```

---

## Cảm biến DHT không đọc được

Kiểm tra:

- Đúng loại DHT11/DHT20.
- Đúng thư viện.
- Đúng chân D3.
- Dây nguồn và GND.
- Không đọc cảm biến quá nhanh.

---

## Air Pressure Sensor không hoạt động

Xác định phiên bản:

```text
BMP280
```

hoặc:

```text
SPA06-003 / SPL07-003
```

Sau đó cài đúng thư viện.

Tài liệu tham khảo sử dụng hai thư viện khác nhau cho BMP280 và SPA06-003. fileciteturn1file8L867-L875

---

# 11. Tài nguyên

## Arduino IDE

https://www.arduino.cc/en/software

## Arduino Documentation

https://docs.arduino.cc/

## Grove Temperature & Humidity Sensor

https://github.com/Seeed-Studio/Grove_Temperature_And_Humidity_Sensor

## SPA06-003 / SPL07-003

https://github.com/Seeed-Studio/Seeed_Arduino_SPA06

## Grove BMP280

https://github.com/Seeed-Studio/Grove_BMP280

## LiquidCrystal I2C

Tìm và cài thư viện `LiquidCrystal I2C` trực tiếp từ Arduino IDE Library Manager.

---

# Sơ đồ học tập đề xuất

```text
Arduino cơ bản
      │
      ├── Digital Output
      │      └── LED
      │
      ├── Digital Input
      │      └── Button
      │
      ├── Analog Input
      │      ├── Potentiometer
      │      ├── Light Sensor
      │      └── Sound Sensor
      │
      ├── PWM / Tone
      │      └── Buzzer
      │
      ├── Serial
      │      ├── Serial Monitor
      │      └── Serial Plotter
      │
      ├── I2C
      │      ├── LCD1602
      │      └── Air Pressure Sensor
      │
      └── Sensor
             └── Temperature & Humidity
```

---

# Lộ trình học MakerEDU Starter Kit

| Bài | Nội dung | Kiến thức chính |
|---:|---|---|
| 1 | LED Blink | Digital Output |
| 2 | Button + LED | Digital Input |
| 3 | Potentiometer | Analog Input |
| 4 | Buzzer | Tone / PWM |
| 5 | Light Sensor | Analog Sensor |
| 6 | Sound Sensor | Analog Sensor + Serial Plotter |
| 7 | LCD1602 | I2C + Library |
| 8 | Temperature & Humidity | Sensor + LCD |
| 9 | Air Pressure | I2C Sensor |
| P1 | Music Rhythm Lamp | Buzzer + LED |
| P2 | Smart Desk Lamp | Light + Sound + LED |
| P3 | Environmental Monitor | Sensor + LCD1602 |

---

# License

Tài liệu và mã nguồn ví dụ trong repository này được cung cấp nhằm mục đích **học tập, nghiên cứu và phát triển dự án Arduino/MakerEDU**.

Khi sử dụng hoặc phát triển lại nội dung, vui lòng giữ thông tin nguồn và bản quyền của các thư viện/phần mềm bên thứ ba theo license tương ứng.

---

## MakerEDU – Learn. Build. Create.

**MakerEDU Starter Kit for Arduino** giúp người mới bắt đầu đi từ những chương trình Arduino đầu tiên đến các ứng dụng cảm biến và hệ thống điều khiển thực tế.

> **Start with Arduino. Build with MakerEDU.**
