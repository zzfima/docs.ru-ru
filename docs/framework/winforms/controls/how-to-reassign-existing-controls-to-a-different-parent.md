---
title: "Практическое руководство. Переназначение существующих элементов управления другим родительским элементам | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "контейнерные элементы управления, Windows Forms"
  - "макет [Windows Forms], изменение размеров"
  - "макет [Windows Forms], дочерние элементы управления"
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Переназначение существующих элементов управления другим родительским элементам
Можно назначать существующие в форме элементы управления новому контейнерному элементу управления.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров**. Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Переназначение существующих элементов управления другим родительским элементам  
  
1.  Перетащите три элемента управления <xref:System.Windows.Forms.Button> с **панели элементов** в форму.  
  
     Расположите их рядом друг с другом, но не выравнивайте.  
  
2.  В **панели элементов** щелкните значок элемента управления <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
     Не перетаскивайте значок на форму.  
  
3.  Переместите указатель мыши к трем элементам управления <xref:System.Windows.Forms.Button>.  
  
     Указатель превратится в перекрестие с прикрепленным значком элемента управления <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
4.  Нажмите и удерживайте кнопку мыши.  
  
5.  Перемещайте указатель мыши, чтобы нарисовать контур элемента управления <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
6.  Обведите таким образом три элемента управления <xref:System.Windows.Forms.Button>.  
  
7.  Отпустите кнопку мыши.  
  
     Теперь три элемента управления <xref:System.Windows.Forms.Button> вставлены в элемент управления <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
## См. также  
 <xref:System.Windows.Forms.FlowLayoutPanel>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [Расположение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)