---
title: "Способы активации элемента управления Button в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08b5359446a80da257f5afec07cc70e3d4aad46b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ways-to-select-a-windows-forms-button-control"></a>Способы активации элемента управления Button в Windows Forms
Кнопки Windows Forms можно выбрать следующими способами:  
  
-   Нажмите кнопку мышью.  
  
-   Кнопка вызова <xref:System.Windows.Forms.Control.Click> события в коде.  
  
-   Перемещение фокуса к кнопке по нажатию клавиши TAB и затем нажмите кнопку, нажав клавишу ПРОБЕЛ или ВВОД.  
  
-   Нажмите клавишу доступа (ALT + подчеркнутая буква) для кнопки. Дополнительные сведения о ключах доступа см. в разделе [как: Создание сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  
  
-   Если кнопка является кнопкой «принять», формы, нажатие клавиши ВВОД активирует кнопку, даже если фокус находится на другом элементе управления, только если этот элемент управления является кнопкой, многострочным текстовым полем или пользовательский элемент управления, который перехватывает клавишу ВВОД.  
  
-   Если кнопка является кнопкой «Отмена» в форме, нажатие клавиши ESC активирует кнопку, даже если другой элемент управления имеет фокус.  
  
-   Вызовите <xref:System.Windows.Forms.Button.PerformClick%2A> метод, чтобы активировать кнопку программными средствами.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
