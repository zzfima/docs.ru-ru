---
title: Общие сведения об элементе управления Label
ms.date: 03/30/2017
f1_keywords:
- Label
helpviewer_keywords:
- images [Windows Forms], displaying in labels
- labels
- Label control [Windows Forms], about Label control
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
ms.openlocfilehash: 1ca14553c7cb51d2b7a329950aeaec4c0439762a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745288"
---
# <a name="label-control-overview-windows-forms"></a>Общие сведения об элементе управления Label (Windows Forms)
Windows Forms элементы управления <xref:System.Windows.Forms.Label> используются для вывода текста или изображений, которые не могут быть изменены пользователем. Они используются для обнаружения объектов в форме — для предоставления описания того, что может делать определенный элемент управления, например, или для вывода сведений в ответ на событие или процесс во время выполнения в приложении. Например, метки можно использовать для добавления описательных субтитров в текстовые поля, списки, поля со списками и т. д. Можно также написать код, который изменяет текст, отображаемый меткой, в ответ на события во время выполнения. Например, если приложению требуется несколько минут для обработки изменений, можно отобразить сообщение о состоянии обработки в метке.  
  
## <a name="working-with-the-label-control"></a>Работа с элементом управления Label  
 Поскольку элемент управления <xref:System.Windows.Forms.Label> не может получать фокус, он также может использоваться для создания ключей доступа для других элементов управления. Ключ доступа позволяет пользователю выбрать другой элемент управления, нажав клавишу ALT с клавишей доступа. Дополнительные сведения см. в разделах [Создание ключей доступа для Windows Forms элементов управления](how-to-create-access-keys-for-windows-forms-controls.md) и [инструкции: создание ключей доступа с помощью элементов управления Label Windows Forms](how-to-create-access-keys-with-windows-forms-label-controls.md).  
  
 Заголовок, отображаемый в метке, содержится в свойстве <xref:System.Windows.Forms.Label.Text%2A>. Свойство <xref:System.Windows.Forms.Label.TextAlign%2A> позволяет задать выравнивание текста внутри метки. Дополнительные сведения см. в разделе [как задать текст, отображаемый элементом управления Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Label>
- [Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms](how-to-create-access-keys-with-windows-forms-label-controls.md)
