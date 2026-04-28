# Резюме

## Контакты

**ФИО:** Михайловский Андрей Васильевич  
**Email:** mihajlovsckij.andrey@yandex.ru  
**GitHub:** https://github.com/djadik0

## Кратко о себе

Начинающий инженер в направлении FPGA / RTL / SoC. Прохожу стажировку в НИЛ ЭСК НИУ МИЭТ по направлению RTL.

Основной интерес — разработка **SoC**, **interconnect architecture**, разработка и интеграция цифровых IP-блоков: memory-mapped периферия, UART, SPI, AXI4-Lite, AXI-Stream, valid-ready интерфейсы, register map design и базовая верификация RTL-модулей.

В портфолио есть как небольшие учебные RTL-модули, так и более крупные интеграционные проекты: **RISC-V mini SoC**, **UART-to-AXI4-Lite bridge**, аппаратный **AI UART classifier**, лабораторные работы по FPGA и набор мини-проектов по интерфейсам и цифровой логике.

## Образование

**Учебное заведение:** Национальный исследовательский университет «Московский институт электронной техники» (НИУ МИЭТ)  
**Курс:** 3 курс  
**Направление / профиль:** Информатика и вычислительная техника  
**Ожидаемая дата окончания:** 2027 год

## Технические навыки

**Языки и HDL:**
- SystemVerilog
- Verilog
- Tcl
- Python

**Инструменты:**
- Xilinx Vivado
- Vivado ILA
- Git / GitHub / Gitlab
- OpenProject 
- Linux
- Python-скрипты для проверки и связи с FPGA

**RTL / FPGA / SoC:**
- FSM
- pipeline
- top-level integration
- memory-mapped peripherals
- register map design
- BRAM / LUTRAM
- FIFO
- DSP-блоки и systolic array concepts
- FPGA prototyping
- XDC / SDC constraints

**Интерфейсы и протоколы:**
- UART RX/TX
- SPI Master
- AXI4-Lite
- AXI-Stream
- valid-ready handshake
- valid-credit 
- AMBA concepts 

**Архитектурные темы:**
- RISC-V RV32I 
- LSU
- CSR
- interrupts
- memory subsystem
- SoC top-level integration
- разработка и подключение простых IP-блоков

**Верификация:**
- простые testbench на SystemVerilog
- проверка RTL в симуляции
- waveform-анализ
- self-checking testbench на базовом уровне

## Навыки, продемонстрированные в проектах

- **SoC / top-level integration:** сборка целостных систем из нескольких RTL-блоков, подключение памяти, периферии, контроллеров и интерфейсных модулей.
- **Memory-mapped периферия:** разработка регистровых блоков, register map, чтение/запись по адресам, частичная запись через byte strobe.
- **Интерфейсные IP-блоки:** UART RX/TX, SPI Master, AXI4-Lite slave, AXI-Stream width converter, valid-ready pipeline stage.
- **FPGA-прототипирование:** подготовка XDC constraints, работа с платой, RGB LED, 7-segment display, UART-связь с ПК.
- **Потоковая обработка данных:** AXI-Stream, backpressure, FIFO, width conversion, valid/ready handshake.
- **Вычислительные RTL-блоки:** matrix multiplier, CNN inference pipeline, conv / pooling / fully-connected / argmax.

## Проекты

### 1. RISC-V Processor System on FPGA

**Стек:** SystemVerilog, C/C++, Vivado  
**Ссылка:** https://github.com/djadik0/riscv-mini-soc-fpga

Учебная 32-битная **RISC-V SoC-система** на SystemVerilog.

Что реализовано:
- процессорное ядро на базе подмножества **RV32I**;
- память инструкций и память данных с инициализацией из `.mem` файлов;
- LSU с поддержкой load/store операций и byte enable;
- CSR-подсистема и базовая обработка trap / interrupt;
- memory-mapped периферия для переключателей и светодиодов;
- контроллер внешних прерываний;
- пример встроенной программы на C/C++ для работы с периферией.


### 2. UART to AXI4-Lite Bridge

**Стек:** SystemVerilog, Python, Vivado, XDC  
**Ссылка:** https://github.com/djadik0/uart_axi_lite

Учебный RTL-проект, в котором ПК через UART управляет AXI4-Lite регистровым блоком на FPGA.

Что реализовано:
- `uart_rx` и `uart_tx` для обмена байтами с ПК;
- `uart_to_axi_lite_master` для преобразования UART-команд в AXI4-Lite read/write транзакции;
- `axi4_lite_slave` с 32-битными регистрами;
- `top_uart_axi_lite` для интеграции UART и AXI4-Lite частей;
- Python-консоль `uart_axi_lite_console.py` для команд `write` и `read`;
- поддержка register map и частичной записи через `WSTRB`;
- testbench для проверки AXI4-Lite slave;
- XDC constraint-файл для FPGA-платы.


### 3. FPGA AI UART Classifier

**Стек:** SystemVerilog, Python, Vivado  
**Ссылка:** https://github.com/djadik0/fpga-ai-uart-classifier

Учебный аппаратный классификатор изображений на FPGA с загрузкой данных по UART и RTL inference pipeline.

Что реализовано:
- загрузка изображения `64x64` с ПК в FPGA по UART;
- `uart_image_loader` и внутренний memory buffer;
- вычислительный RTL-конвейер: convolution layer, max-pooling, fully-connected layer, argmax;
- хранение весов в `.mem` файлах;
- Python-часть для обучения модели, экспорта весов и отправки изображений;
- полный top-level тракт `UART RX -> memory -> conv -> pooling -> FC -> argmax -> UART TX`;
- testbench полного уровня и XDC constraints.


### 4. FPGA / RTL Labs

**Стек:** SystemVerilog, Tcl, Vivado  
**Ссылка:** https://github.com/djadik0/FPGA_labs

Репозиторий с лабораторными работами по FPGA, RTL-проектированию и автоматизации Vivado.

Основные темы:
- Tcl-автоматизация создания проекта в Vivado;
- LUT, CARRY и триггеры;
- DSP-ячейки;
- LUTRAM и BRAM;
- pipelines и systolic arrays;
- valid-ready, AXI-Stream и credit flow control.


### 5. RTL / FPGA Practice

**Стек:** SystemVerilog, Vivado, SDC  
**Ссылка:** https://github.com/djadik0/rtl-fpga-practice

Репозиторий с небольшими RTL-задачами и мини-проектами.

Внутри есть:
- 4-битный ALU;
- BCD-counter;
- FSM автомата продажи кофе;
- counter на FSM;
- flatten layer;
- valid-ready pipeline stage;
- pulse generator / waveform project;
- SDC constraints для `MY_DESIGN`;
- SPI Master;
- AXI-Stream Width Converter 32-to-8.

### 6. RGB LED and 7-Segment Display Controller for Nexys A7-100T

**Стек:** SystemVerilog, XDC  
**Ссылка:** https://github.com/djadik0/RGB-LED

Учебный FPGA-проект для платы **Nexys A7-100T**.

Что реализовано:
- управление встроенным RGB LED через PWM;
- разбиение значения переключателей на RGB-компоненты;
- формирование 24-битного `hex_RGB`;
- вывод значения на 6-разрядный 7-segment display;
- динамическое мультиплексирование разрядов индикатора;
- hex-to-7-segment decoder;
- простой testbench;
- XDC constraints под реальную FPGA-плату.


### 7. Matrix Multiplier on SystemVerilog

**Стек:** SystemVerilog  
**Ссылка:** https://github.com/djadik0/Matrix-Multiplier

Параметризуемый модуль умножения квадратных матриц на SystemVerilog.

Что реализовано:
- параметризуемый размер матрицы;
- параметризуемая разрядность элементов;
- последовательное вычисление через FSM;
- операция multiply-accumulate;
- внутренний аккумулятор;
- сигнал `done` после завершения вычислений;
- состояния автомата для запуска, MAC, сохранения ячейки, перехода к следующей ячейке и завершения.


## Опыт работы / стажировки

### НИЛ ЭСК, НИУ МИЭТ — лаборант, RTL / цифровое проектирование

**Период:** декабрь 2025 — настоящее время  
**Организация:** Научно-исследовательская лаборатория «Энергоэффективные системы на кристалле» (НИЛ ЭСК), Национальный исследовательский университет «МИЭТ»

- Работаю в лаборатории по направлению **RTL / цифровое проектирование / SystemVerilog**.
- Участвую в учебно-исследовательских и инженерных задачах, связанных с разработкой и анализом RTL-модулей.
- Выполняю аппаратную отладку RTL-дизайнов на FPGA с использованием Vivado ILA: анализирую внутренние сигналы, состояния FSM и интерфейсные обмены на реальной плате.

### НИЛ ЭСК, НИУ МИЭТ — стажёр, RTL / цифровое проектирование

**Период:** октябрь 2025 — ноябрь 2025  
**Организация:** Научно-исследовательская лаборатория «Энергоэффективные системы на кристалле» (НИЛ ЭСК), Национальный исследовательский университет «МИЭТ»

- Проходил стажировку по направлению **RTL / цифровое проектирование / SystemVerilog**.
- Знакомился со структурой RTL-проектов, FPGA-прототипированием и процессом проверки цифровых модулей.
- Выполнял учебно-инженерные задачи: запуск симуляций, анализ waveform, работа с Vivado и разбор RTL-модулей.

## Достижения / мероприятия

- **5 место — хакатон / соревнование по проектированию СнК 2026**
  - **Трек:** RTL
  - **Год:** 2026
