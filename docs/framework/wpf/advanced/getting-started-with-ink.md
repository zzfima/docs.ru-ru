---
title: "Начало работы с рукописными данными | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "анимация, цвета кистей с градиентом"
  - "кисти, анимация цветов"
  - "градиентная кисть, анимация цветов"
  - "процедурный код вместо XAML"
  - "XAML, процедурный код вместо"
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Начало работы с рукописными данными
Включение цифровых рукописных данных в приложения стало проще, чем когда\-либо.  Рукописные данные развились от дополнения к COM и методу программирования Windows Forms до достижения полной интеграции в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Устанавливать отдельные пакеты SDK или библиотеки времени выполнения не требуется.  
  
## Предварительные требования  
 Для использования следующих примеров необходимо сначала установить Microsoft Visual Studio 2005 и [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].  Также следует понимать порядок написания приложений для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Дополнительные сведения о начале работы с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## Быстрое руководство  
 Этот раздел помогает написать простое приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для сбора данных рукописного ввода.  
  
 Установите Microsoft Visual Studio 2005 и [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)], если это еще не сделано.  Обычно приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] перед просмотром должны быть скомпилированы, даже если они состоят только из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Однако [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] включает приложение XamlPad, созданное для ускорения процесса реализации пользовательского интерфейса на основе [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Это приложение можно использовать для просмотра и ознакомления с несколькими первыми примерами данного документа.  Процесс создания компилируемых приложений из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] рассматривается далее в этом документе.  
  
 Чтобы запустить XAMLPad, нажмите кнопку **Пуск**, а затем последовательно выберите команды **Все программы**, **Microsoft Windows SDK**, **Средства** и **XAMLPad**.  В области отрисовки XAMLPad отображается визуализация кода XAML, написанного в области кода.  Можно редактировать код XAML, и изменения сразу отражаются в области отрисовки.  
  
#### Есть рукописные данные?  
 Чтобы запустить первое приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с поддержкой рукописного ввода:  
  
1.  Откройте Microsoft Visual Studio 2005  
  
2.  Создать новое **Приложение Windows \(WPF\)**  
  
3.  Введите `<InkCanvas/>` между тегами `<Grid>`  
  
4.  Нажмите клавишу **F5** для запуска приложения в отладчике  
  
5.  Используя перо или мышь, напишите Hello world в окне  
  
 Вы написали рукописный эквивалент приложения "Hello world" нажатием всего 12 клавиш\!  
  
#### Добавьте изюминку в приложение  
 Воспользуемся преимуществами некоторых возможностей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Замените все содержимое между открывающим \<Window\> и закрывающим \<\/Window\> тегами следующей разметкой, чтобы получить градиентный фон поверхности рукописного ввода.  
  
 [!code-xml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### Использование анимации  
 Давайте развлечемся анимацией цветов кисти градиента.  Добавьте следующий код [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] после закрывающего тега `</InkCanvas>`, но перед закрывающим тегом `</Page>`.  
  
 [!code-xml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### Добавление кода программной части XAML  
 Хотя XAML очень сильно упрощает разработку пользовательского интерфейса, любому реальному приложению необходим код для обработки событий.  Ниже приведен простой пример увеличения рукописных данные в ответ на щелчок правой кнопкой мыши:  
  
 Установите обработчик `MouseRightButtonUp` в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 В обозревателе решений Visual Studio разверните Windows1.xaml и откройте файл кода программной части Window1.xaml.cs или Window1.xaml.vb, если используется Visual Basic.  Добавьте следующий код обработчика событий:  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 Теперь запустите приложение.  Добавьте рукописные данные и щелкните правой кнопкой мыши или выполните эквивалентное нажатие и удерживание с помощью пера.  
  
#### Использование процедурного кода вместо XAML  
 Можно получить доступ ко всем возможностям [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] из процедурного кода.  Вот приложение "Hello Ink World" для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], которое вообще не использует [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Вставьте следующий код в пустое консольное приложение в Visual Studio.  Добавьте ссылки на сборки PresentationCore, PresentationFramework и WindowsBase и постройте приложение нажатием клавиши **F5**:  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## См. также  
 [Рукописный ввод](../../../../docs/framework/wpf/advanced/digital-ink.md)   
 [Сбор рукописных данных](../../../../docs/framework/wpf/advanced/collecting-ink.md)   
 [Распознавание рукописного ввода](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)   
 [Хранение рукописных данных](../../../../docs/framework/wpf/advanced/storing-ink.md)