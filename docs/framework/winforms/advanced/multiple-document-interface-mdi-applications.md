---
title: Приложения с интерфейсом MDI
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 23e0275d5e6b081ec02d669a78e8695453360637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956549"
---
# <a name="multiple-document-interface-mdi-applications"></a>Приложения с интерфейсом MDI
Приложения с многодокументным интерфейсом (MDI) позволяют отображать несколько документов одновременно, при этом каждый документ отображается в отдельном окне. Приложения MDI часто имеют пункт меню «окно» с подменю для переключения между окнами или документами.  
  
> [!NOTE]
> Существуют различия в поведении между формами MDI и окнами однодокументного интерфейса (SDI) в Windows Forms. `Opacity` Свойство не влияет на внешний вид дочерних форм MDI. Кроме того, <xref:System.Windows.Forms.Form.CenterToParent%2A> метод не влияет на поведение дочерних форм MDI.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md)  
 Инструкции по созданию контейнера для нескольких документов в приложении MDI.  
  
 [Практическое руководство. Создание дочерних форм MDI](how-to-create-mdi-child-forms.md)  
 Инструкции по созданию одного или нескольких окон, которые работают в родительской форме MDI.  
  
 [Практическое руководство. Определение активной дочерней MDI-формы](how-to-determine-the-active-mdi-child.md)  
 Инструкции по проверке дочернего окна, имеющего фокус (и отправке его содержимого в буфер обмена).  
  
 [Практическое руководство. Отправка данных в активную дочернюю MDI-форму](how-to-send-data-to-the-active-mdi-child.md)  
 Инструкции по переносу сведений в активное дочернее окно.  
  
 [Практическое руководство. Расположить дочерние формы MDI](how-to-arrange-mdi-child-forms.md)  
 Инструкции по мозаичному разбиению, каскаду или упорядочению дочерних окон приложения MDI.
