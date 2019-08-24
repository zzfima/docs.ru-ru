---
title: Практическое руководство. Добавление элементов управления, для которых не существует пользовательского интерфейса, в формы Windows Forms
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
ms.openlocfilehash: bc1f844e5a2cf4d4f3b64ebf20e935f36ff85e12
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987092"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Практическое руководство. Добавление элементов управления, для которых не существует пользовательского интерфейса, в формы Windows Forms

Невизуальный элемент управления (или компонент) предоставляет приложению функциональные возможности. В отличие от других элементов управления, компоненты не предоставляют пользователю пользовательский интерфейс и, таким образом, не должны отображаться на поверхности конструктор Windows Forms. При добавлении компонента в форму конструктор Windows Forms отображает область с изменяемым размером в нижней части формы, где отображаются все компоненты. После добавления элемента управления в область компонентов можно выбрать компонент и задать его свойства так же, как любой другой элемент управления в форме.

## <a name="add-a-component-to-a-windows-form"></a>Добавление компонента в форму Windows Forms

1. Откройте форму в Visual Studio. Подробную информацию см. в разделе [Практическое руководство. Отображение Windows Forms в конструкторе](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).

2. На **панели элементов** щелкните компонент и перетащите его на форму.

     Ваш компонент появится в области компонентов.

Более того, компоненты можно добавлять в форму во время выполнения. Это распространенный сценарий, особенно потому, что компоненты не имеют визуального выражения, в отличие от элементов управления с пользовательским интерфейсом. В приведенном ниже <xref:System.Windows.Forms.Timer> примере компонент добавляется во время выполнения. (Обратите внимание, что Visual Studio содержит ряд различных таймеров; в этом случае используйте компонент Windows Forms <xref:System.Windows.Forms.Timer> . Дополнительные сведения о различных таймерах в Visual Studio см. в статье [Введение в серверные таймеры](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).

> [!CAUTION]
> Компоненты часто имеют особые свойства, которые должны быть заданы для их эффективной работы. В случае использования компонента <xref:System.Windows.Forms.Timer> в приведенном ниже примере задается свойство `Interval`. Убедитесь, что при добавлении компонентов в проект вы задаете необходимые свойства этих компонентов.

## <a name="add-a-component-to-a-windows-form-programmatically"></a>Добавление компонента в форму Windows программным способом

1. Создайте экземпляр класса <xref:System.Windows.Forms.Timer> в коде.

2. Задайте свойство `Interval` для определения времени между тактами таймера.

3. Настройте другие необходимые свойства для компонента.

     В следующем коде показано создание <xref:System.Windows.Forms.Timer> и установка его свойства `Interval`.

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

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Практическое руководство. Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Практическое руководство. Добавление элементов управления ActiveX в Windows Forms](how-to-add-activex-controls-to-windows-forms.md)
- [Размещение элементов управления в формах Windows Forms](putting-controls-on-windows-forms.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
