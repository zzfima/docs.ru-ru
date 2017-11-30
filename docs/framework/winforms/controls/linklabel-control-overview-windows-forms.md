---
title: "Общие сведения об элементе управления LinkLabel (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0cb01c0fc5503a5bf16e1f191d87ae90907ec816
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="linklabel-control-overview-windows-forms"></a>Общие сведения об элементе управления LinkLabel (Windows Forms)
Windows Forms <xref:System.Windows.Forms.LinkLabel> позволяет добавить веб-ссылок в приложениях Windows Forms. Можно использовать <xref:System.Windows.Forms.LinkLabel> управления для всех элементов, можно использовать <xref:System.Windows.Forms.Label> элемента управления; в тексте можно задать как ссылка на файл, папку или веб-страницы.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Что можно сделать с помощью элемента управления LinkLabel  
 Помимо свойств, методов и событий <xref:System.Windows.Forms.Label> управления <xref:System.Windows.Forms.LinkLabel> элемент управления имеет свойства для гиперссылок и цвета ссылок. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Свойство задает область текста, которая активирует ссылку. <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, И <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> свойства задать цвета ссылки. <xref:System.Windows.Forms.LinkLabel.LinkClicked> Событий определяет, что происходит при выборе текста ссылки.  
  
 Простейшего использования <xref:System.Windows.Forms.LinkLabel> управления является отображение одну связь с помощью <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> свойство, но также может отображаться несколько гиперссылки с помощью <xref:System.Windows.Forms.LinkLabel.Links%2A> свойство. <xref:System.Windows.Forms.LinkLabel.Links%2A> Свойство позволяет получить доступ к коллекции ссылок. Можно также указать данные в <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> свойства каждого отдельного <xref:System.Windows.Forms.LinkLabel.Link> объекта. Значение <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> свойство может использоваться для хранения расположение файла для отображения или адрес веб-сайта.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.LinkLabel>  
 [Общие сведения об элементе управления Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
