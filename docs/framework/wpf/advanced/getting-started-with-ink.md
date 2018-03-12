---
title: "Начало работы с рукописными данными"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 74227ebe815e971087569ff39ac0a3479c1b0d14
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="getting-started-with-ink"></a>Начало работы с рукописными данными
Включение рукописного ввода в приложения проще, чем когда-либо. Рукописный ввод развивался с дополнения метод COM и Windows Forms программирования для достижения полной интеграции в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Необходимо установить отдельные пакеты SDK или библиотеки времени выполнения.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы использовать следующие примеры, необходимо сначала установить Microsoft Visual Studio 2005 и [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. Кроме того, необходимо иметь представление о создании приложений для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Дополнительные сведения о начале работы с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], в разделе [Пошаговое руководство: My первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="quick-start"></a>Быстрый запуск  
 Этот раздел помогает написать простое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложение, которое собирает рукописного ввода.  
  
 Если это еще не сделано, установите Microsoft Visual Studio 2005 и [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)]. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Обычно приложения должны быть скомпилированы перед просмотром, даже если они состоят только из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Тем не менее [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] включает в себя приложения, средство XamlPad, позволяющий ускорить процесс реализации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-на основе пользовательского интерфейса. Это приложение можно использовать для просмотра и ознакомления с несколькими первыми примерами данного документа. Процесс создания компилируемых приложений из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] рассматривается далее в этом документе.  
  
 Чтобы запустить средство XAMLPad, нажмите **запустить** последовательно выберите пункты **все программы**, пункты **Microsoft Windows SDK**, пункты **средства**и нажмите кнопку **XAMLPad**. В области отрисовки XAMLPad отображается визуализация кода XAML, написанного в области кода. Можно изменить код XAML, а изменения немедленно отражаются в области отрисовки.  
  
#### <a name="got-ink"></a>У вас есть рукописного ввода?  
 Чтобы запустить первое [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложения с поддержкой рукописного ввода:  
  
1.  Откройте Microsoft Visual Studio 2005  
  
2.  Создайте новый **приложения Windows (WPF)**  
  
3.  Тип `<InkCanvas/>` между `<Grid>` тегов  
  
4.  Нажмите клавишу **F5** для запуска приложения в отладчике  
  
5.  Используя перо или мышь, напишите **Здравствуй, мир!** в окне  
  
 Вы написали рукописный эквивалент приложения «hello world» с всего 12 клавиш!  
  
#### <a name="spice-up-your-application"></a>Изюминку в приложение  
 Воспользуемся преимуществами некоторых возможностей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Замените весь код между открывающим \<окна > и закрытие \</Window > теги с следующую разметку, чтобы получить градиентный фон поверхности рукописного ввода.  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a>С помощью анимации  
 Для практики давайте анимация цвета градиента кисти. Добавьте следующие [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] после закрывающего `</InkCanvas>` тег, но перед закрывающим тегом `</Page>` тег.  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a>Добавление кода программной части XAML  
 Хотя XAML позволяет очень легко разработать пользовательский интерфейс, любые реальных приложений необходимо добавить код для обработки событий. Ниже приведен простой пример увеличения рукописного ввода в ответ на щелчок правой кнопкой мыши:  
  
 Задать `MouseRightButtonUp` обработчик в вашей [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 В обозревателе решений Visual Studio разверните Windows1.xaml и откройте файл кода Window1.xaml.cs или Window1.xaml.vb при использовании Visual Basic. Добавьте следующий код обработчика событий:  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 Теперь запустите приложение. Добавьте рукописные и правой кнопкой мыши или нажатие и удерживание эквивалента с помощью пера.  
  
#### <a name="using-procedural-code-instead-of-xaml"></a>С использованием процедурного кода вместо XAML  
 Можно получить доступ ко всем [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] функций из процедурного кода. Вот приложение «Hello Ink World» для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , не использует [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] вообще. Вставьте приведенный ниже код в пустое консольное приложение в Visual Studio. Добавление ссылки на сборки PresentationCore и PresentationFramework, WindowsBase и построить приложение, нажав клавишу **F5**:  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Рукописный ввод](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [Сбор рукописных данных](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [Распознавание рукописного ввода](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [Хранение рукописных данных](../../../../docs/framework/wpf/advanced/storing-ink.md)
