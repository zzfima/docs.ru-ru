---
title: Создание InkCanvas в приложении WPF в Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: ebbf25037921e7802b2bfcb6ffa562d16a849ffa
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920253"
---
# <a name="get-started-with-ink-in-wpf"></a>Начало работы с рукописным вводом в WPF

Windows Presentation Foundation (WPF) имеет функцию рукописного ввода, которая упрощает внедрение цифровых рукописных данных в приложение.

## <a name="prerequisites"></a>Необходимые компоненты

Чтобы использовать следующие примеры, сначала установите [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). Кроме того, он помогает понять, как писать базовые приложения WPF. Сведения о начале работы с WPF см. в разделе [Пошаговое руководство. мое первое классическое приложение WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="quick-start"></a>Быстрое начало

Этот раздел поможет вам написать простое приложение WPF, собирающее рукописный ввод.

### <a name="got-ink"></a>У вас есть рукописный ввод?

Создание приложения WPF, поддерживающего рукописный ввод:

1. Запустите Visual Studio.

2. Создайте новое **приложение WPF**.

   В диалоговом окне **Новый проект** разверните узел **установленные** > **Visual C#**  или **Visual Basic** > **Windows Desktop** . Затем выберите шаблон приложения **WPF (.NET Framework)** . Введите имя и нажмите кнопку **ОК**.

   Visual Studio создаст проект, а файл *MainWindow. XAML* откроется в конструкторе.

3. Введите `<InkCanvas/>` между тегами `<Grid>`.

   ![Конструктор XAML с тегом InkCanvas](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. Нажмите клавишу **F5** , чтобы запустить приложение в отладчике.

5. С помощью пера или мыши напишите **Hello World** в окне.

Вы написали рукописный эквивалент приложения "Hello World" только с 12 нажатиями!

### <a name="spice-up-your-app"></a>Воссоздание приложения

Давайте попробуем воспользоваться преимуществами некоторых функций WPF. Замените все между открывающим и закрывающим \<окном > тегами следующей разметкой:

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

Этот XAML создает фон градиентной кисти на поверхности рукописного ввода.

![Градиентные цвета на поверхности рукописного ввода в приложении WPF](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a>Добавьте код, лежащий в основе XAML

Хотя XAML упрощает проектирование пользовательского интерфейса, любое реальное приложение должно добавлять код для работы с событиями. Ниже приведен простой пример, который позволяет увеличить рукописный ввод в ответ на щелчок правой кнопкой мыши.

1. Задайте обработчик `MouseRightButtonUp` в коде XAML:

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. В **Обозреватель решений**разверните MainWindow. XAML и откройте файл кода программной части (MainWindow.XAML.cs или MainWindow. XAML. vb). Добавьте следующий код обработчика событий:

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. Запустите приложение. Добавьте рукописный ввод, а затем щелкните его правой кнопкой мыши или выполните нажатие клавиши с пером.

   Экран увеличивается при каждом щелчке правой кнопкой мыши.

### <a name="use-procedural-code-instead-of-xaml"></a>Использование процедурного кода вместо XAML

Вы можете получить доступ ко всем функциям WPF из процедурного кода. Выполните следующие действия, чтобы создать приложение "Привет для рукописного ввода" для WPF, которое вообще не использует XAML.

1. Создайте новый проект консольного приложения в Visual Studio.

   В диалоговом окне **Новый проект** разверните узел **установленные** > **Visual C#**  или **Visual Basic** > **Windows Desktop** . Затем выберите шаблон приложения " **консольное приложение" (.NET Framework)** . Введите имя и нажмите кнопку **ОК**.

1. Вставьте следующий код в файл Program.cs или Program. vb:

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. Добавьте ссылки на сборки PresentationCore, PresentationFramework и WindowsBase, щелкнув правой кнопкой мыши **ссылки** в **Обозреватель решений** и выбрав **Добавить ссылку**.

   ![Диспетчер ссылок, отображающий PresentationCore и PresentationFramework](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. Постройте приложение, нажав клавишу **F5**.

## <a name="see-also"></a>См. также

- [Рукописный ввод](digital-ink.md)
- [Сбор рукописных данных](collecting-ink.md)
- [Распознавание рукописного ввода](handwriting-recognition.md)
- [Хранение рукописных данных](storing-ink.md)
