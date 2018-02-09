---
title: "Практическое руководство. Добавление элементов управления, для которых не существует пользовательского интерфейса, в формы Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3abbf931cff9ad459e8c9221f91430ecccefa9cc
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Практическое руководство. Добавление элементов управления, для которых не существует пользовательского интерфейса, в формы Windows Forms
Невидимый элемент управления (или компонент) предоставляет определенные функциональные возможности для приложения. В отличие от других элементов управления, компоненты не предоставляют пользовательский интерфейс и, таким образом, не нуждаются в отображении в рабочей области конструктора Windows Forms. При добавлении компонента на форму конструктор Windows Forms отображает область изменяемого размера в нижней части формы, в которой отображаются все компоненты. После добавления элемента управления в область компонентов, можно выбрать компонент и задать его свойства, как и для любого другого элемента управления на форме.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-component-to-a-windows-form"></a>Добавление компонента в форму Windows Forms  
  
1.  Откройте форму. Дополнительные сведения см. в разделе [Практическое руководство. Отображение форм Windows Forms в конструкторе](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  На **панели элементов** щелкните компонент и перетащите его на форму.  
  
     Компонент появится в области компонентов.  
  
 Кроме того компоненты могут добавляться в форму во время выполнения. Это распространенный сценарий, особенно из-за того, что компоненты не имеют визуального выражения, в отличие от элементов управления, имеющих пользовательский интерфейс. В следующем примере компонент <xref:System.Windows.Forms.Timer> добавляется во время выполнения. (Обратите внимание, что [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] содержит ряд различных таймеров; в данном случае используйте компонент <xref:System.Windows.Forms.Timer> Windows Forms. Дополнительные сведения о других таймерах в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] см. в разделе [Общие сведения о серверных таймерах](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)  
  
> [!CAUTION]
>  Компоненты часто имеют особые свойства, которые должны быть заданы для их эффективной работы. В случае использования компонента <xref:System.Windows.Forms.Timer> в приведенном ниже примере задается свойство `Interval`. Убедитесь, что при добавлении компонентов в проект вы задаете необходимые свойства этих компонентов.
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a>Добавление компонента в форму Windows Forms программными средствами  
  
1.  Создайте экземпляр класса <xref:System.Windows.Forms.Timer> в коде.  
  
2.  Задайте свойство `Interval` для определения времени между тактами таймера.  
  
3.  Настройте другие необходимые свойства компонента.  
  
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
    >  Создание ссылки на вредоносный элемент `UserControl` может поставить локальный компьютер под угрозу атаки по сети. Это может произойти только в том случае, если злоумышленник создаст небезопасный пользовательский элемент управления, а затем вы по ошибке добавите его в проект.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [Практическое руководство. Копирование элементов управления между формами Windows Forms](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [Размещение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Функциональная классификация элементов управления Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
