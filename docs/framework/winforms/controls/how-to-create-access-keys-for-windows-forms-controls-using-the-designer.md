---
title: "Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed3bf2aa1e6081ca018f1b4dec98e6304a1aa95c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора
*Ключ доступа* — это подчеркнутый символ в тексте меню, пункт меню или метки элемента управления, например кнопки. Он позволяет пользователю «нажмите кнопку» с помощью клавиши ALT и клавишу с буквой. Например, если кнопка запускает процесс печати формы и, следовательно, его `Text` свойство имеет значение «Print», добавив амперсанд (&) перед буквой «P» буква «P» подчеркнуть в тексте кнопки во время выполнения. Пользователь может запускать команды, связанные с кнопкой, нажав сочетание клавиш ALT + P. Не может иметь клавишу доступа для элемента управления, который не может получить фокус.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-access-key-for-a-control"></a>Чтобы создать сочетание клавиш для элемента управления  
  
1.  В **свойства** задайте `Text` свойства в строку, содержащую знак амперсанда (&) перед буквой, которая будет использоваться в сочетании клавиш. Например, чтобы задать буквы «P» как клавиша доступа, введите **& Печать** в сетку.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Button>  
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
