---
title: Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: ca049e86ab53fbd84cb24e81b0a850050ec2823f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2018
ms.locfileid: "46702924"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>Практическое руководство. Создание кнопки принятия в формах Windows Forms с помощью конструктора
В любой форме Windows, можно назначить <xref:System.Windows.Forms.Button> отображения элемента управления "Принять", также известный как кнопка по умолчанию. Каждый раз, когда пользователь нажимает клавишу ВВОД, нажатии кнопки по умолчанию, независимо от того, что другой элемент управления в форме имеет фокус. Исключение составляют случаи, когда элемент управления с фокусом является еще одну кнопку — в этом случае будет нажата кнопка с фокусом, или многострочного текстового окна, или пользовательский элемент управления, который перехватывает клавишу ВВОД.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-designate-the-accept-button"></a>Чтобы создать кнопку «принять»  
  
1.  Выберите форму, в которой находится кнопка.  
  
2.  В **свойства** формы задайте окне <xref:System.Windows.Forms.Form.AcceptButton%2A> свойства <xref:System.Windows.Forms.Button> имя элемента управления.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Общие сведения об элементе управления Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Способы активации элемента управления Button в Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [Практическое руководство. Создание кнопки отмены в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [Элемент управления Button](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
