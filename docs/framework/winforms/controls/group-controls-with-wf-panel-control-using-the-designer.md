---
title: "Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1c6dd45d2070c77b34c66388b397bb784215654
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Практическое руководство. Группирование элементов управление с элементом управления Panel в формах Windows Forms с помощью конструктора
Windows Forms <xref:System.Windows.Forms.Panel> элементы управления используются для группировки других элементов управления. Существуют три причины для группировки элементов управления. Первая — визуальная группировка связанных элементов форм для упрощения пользовательского интерфейса; Вторая — программная Группировка, переключателей, например; третья — перемещение элементов управления как единое целое, во время разработки.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-group-of-controls"></a>Чтобы создать группу элементов управления  
  
1.  Перетащите <xref:System.Windows.Forms.Panel> управления из **Windows Forms** вкладки области элементов на форму.  
  
2.  Добавьте другие элементы управления в панель путем рисования каждого элемента внутри панели.  
  
     При наличии существующих элементов управления, которые требуется включить в панель, можно выбрать все элементы управления, вырезать их в буфер обмена, выберите <xref:System.Windows.Forms.Panel> управления, а затем вставить их в панель. Также можно перетащить их в панель.  
  
3.  (Необязательно) Если вы хотите добавить границу панели, задайте его <xref:System.Windows.Forms.BorderStyle> свойство. Существует три варианта: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>, и <xref:System.Windows.Forms.BorderStyle.None>.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Практическое руководство. Установка фона панели](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)
