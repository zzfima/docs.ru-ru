---
title: Добавление элементов управления, для которых не существует пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 43f13b4f009fcd6e5d82fa2c00113a77d48877b6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744753"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Практическое руководство. Добавление элементов управления, для которых не существует пользовательского интерфейса, в формы Windows Forms

Невизуальный элемент управления (или компонент) предоставляет приложению функциональные возможности. В отличие от других элементов управления, компоненты не предоставляют пользователю пользовательский интерфейс и, таким образом, не должны отображаться на поверхности конструктор Windows Forms. При добавлении компонента в форму конструктор Windows Forms отображает область с изменяемым размером в нижней части формы, где отображаются все компоненты. После добавления элемента управления в область компонентов можно выбрать компонент и задать его свойства так же, как любой другой элемент управления в форме.

## <a name="add-a-component-to-a-windows-form"></a>Добавление компонента в форму Windows Forms

1. Откройте форму в Visual Studio. Дополнительные сведения см. в разделе [инструкции. отображение Windows Forms в конструкторе](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. В **области элементов**щелкните компонент и перетащите его в форму.

     Ваш компонент появится в области компонентов.

Более того, компоненты можно добавлять в форму во время выполнения. Это распространенный сценарий, особенно потому, что компоненты не имеют визуального выражения, в отличие от элементов управления с пользовательским интерфейсом. В приведенном ниже примере компонент <xref:System.Windows.Forms.Timer> добавляется во время выполнения. (Обратите внимание, что Visual Studio содержит ряд различных таймеров; в этом случае используйте компонент <xref:System.Windows.Forms.Timer> Windows Forms. Дополнительные сведения о различных таймерах в Visual Studio см. в статье [Введение в серверные таймеры](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).

> [!CAUTION]
> Компоненты часто имеют особые свойства, которые должны быть заданы для их эффективной работы. В случае указанного ниже компонента <xref:System.Windows.Forms.Timer> задается свойство `Interval`. Убедитесь, что при добавлении компонентов в проект вы задаете необходимые свойства этих компонентов.

## <a name="add-a-component-to-a-windows-form-programmatically"></a>Добавление компонента в форму Windows программным способом

1. Создайте экземпляр класса <xref:System.Windows.Forms.Timer> в коде.

2. Задайте свойство `Interval`, чтобы определить время между тактами таймера.

3. Настройте другие необходимые свойства для компонента.

     В следующем коде показано создание <xref:System.Windows.Forms.Timer> с набором свойств `Interval`.

    ```vb
    Public Sub CreateTimer()
       Dim timerKeepTrack As New System.Windows.Forms.Timer
       timerKeepTrack.Interval = 1000
    End Sub
    ```

    ```csharp
    public void createTimer()
    {
       System.Windows.Forms.Timer timerKeepTrack = new
           System.Windows.Forms.Timer();
       timerKeepTrack.Interval = 1000;
    }
    ```

    ```cpp
    public:
       void createTimer()
       {
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew
             System::Windows::Forms::Timer();
          timerKeepTrack->Interval = 1000;
       }
    ```

    > [!IMPORTANT]
    > Создание ссылки на вредоносный элемент `UserControl` может поставить локальный компьютер под угрозу атаки по сети. Это может произойти только в том случае, если злоумышленник создаст небезопасный пользовательский элемент управления, а затем вы по ошибке добавите его в проект.

## <a name="see-also"></a>См. также раздел

- [Элементы управления Windows Forms](index.md)
- [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms](how-to-add-activex-controls-to-windows-forms.md)
- [Размещение элементов управления в формах Windows Forms](putting-controls-on-windows-forms.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
