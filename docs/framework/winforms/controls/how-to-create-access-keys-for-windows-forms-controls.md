---
title: "Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms"
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
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81aa68a65d09b073b117f4d96dfc06e614d68aea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms
*Ключ доступа* — это подчеркнутый символ в тексте меню, пункт меню или метки элемента управления, например кнопки. С помощью ключа доступа пользователь может «щелкните» кнопки с помощью клавиши ALT и клавишу с буквой. Например, если кнопка запускает процесс печати формы и, следовательно, его `Text` свойство имеет значение «Print», добавив амперсанд перед буквой «P» вызывает буквы «P» подчеркнуть в тексте кнопки во время выполнения. Пользователь может запускать команды, связанные с кнопкой, нажав сочетание клавиш ALT + P. Не может иметь клавишу доступа для элемента управления, который не может получить фокус.  
  
### <a name="to-create-an-access-key-for-a-control"></a>Чтобы создать сочетание клавиш для элемента управления  
  
1.  Задать `Text` свойства в строку, содержащую знак амперсанда (&) перед буквой, которая будет использоваться в сочетании клавиш.  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  Чтобы включить знак амперсанда в заголовок без создания ключа доступа, добавьте два амперсанда (& &). Один знак амперсанда, отображаемый в заголовке и без символов будут подчеркнуты.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Button>  
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
