---
title: Общие сведения об элементе управления LinkLabel
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 9837902bf56a402d623adbcf41558dcc568b7105
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745222"
---
# <a name="linklabel-control-overview-windows-forms"></a>Общие сведения об элементе управления LinkLabel (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.LinkLabel> позволяет добавлять веб-ссылки в приложения Windows Forms. Элемент управления <xref:System.Windows.Forms.LinkLabel> можно использовать для всех элементов, для которых можно использовать элемент управления <xref:System.Windows.Forms.Label>. можно также задать часть текста в виде ссылки на файл, папку или веб-страницу.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Что можно сделать с помощью элемента управления LinkLabel  
 В дополнение ко всем свойствам, методам и событиям элемента управления <xref:System.Windows.Forms.Label> элемент управления <xref:System.Windows.Forms.LinkLabel> имеет свойства для гиперссылок и цветов ссылок. Свойство <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> задает область текста, которая активирует ссылку. Свойства <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>и <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> задают цвета ссылки. Событие <xref:System.Windows.Forms.LinkLabel.LinkClicked> определяет, что происходит при выборе текста ссылки.  
  
 Самым простым использованием элемента управления <xref:System.Windows.Forms.LinkLabel> является отображение одной ссылки с помощью свойства <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, но можно также отобразить несколько гиперссылок с помощью свойства <xref:System.Windows.Forms.LinkLabel.Links%2A>. Свойство <xref:System.Windows.Forms.LinkLabel.Links%2A> позволяет получить доступ к коллекции ссылок. Можно также указать данные в свойстве <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> каждого отдельного объекта <xref:System.Windows.Forms.LinkLabel.Link>. Значение свойства <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> можно использовать для хранения расположения файла, который необходимо отобразить, или адреса веб-сайта.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.LinkLabel>
- [Общие сведения об элементе управления Label](label-control-overview-windows-forms.md)
- [Практическое руководство. Создание связи с объектом или веб-страницей с помощью элемента управления LinkLabel в Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Практическое руководство. Изменение внешнего вида элемента управления LinkLabel в Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
