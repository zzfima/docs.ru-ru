---
title: "Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 50289e090618d75576eecf2db87f85bd51159fb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора
В любой форме Windows Forms можно назначить <xref:System.Windows.Forms.Button> элемента управления "Отмена". Каждый раз, когда пользователь нажимает клавишу ESC, независимо от других элементов управления в форме имеет фокус по нажатию кнопки "Отмена". Такая кнопка обычно создается, чтобы пользователь мог быстро прервать операцию, не выполняя никаких действий.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-designate-the-cancel-button"></a>Чтобы создать кнопку «Отмена»  
  
1.  Выберите форму, в которой находится кнопка.  
  
2.  В **свойства** задайте формы <xref:System.Windows.Forms.Form.CancelButton%2A> свойства <xref:System.Windows.Forms.Button> имя элемента управления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
