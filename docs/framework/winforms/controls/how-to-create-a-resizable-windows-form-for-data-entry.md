---
title: Практическое руководство. Создание переменного размера Windows формы для ввода данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms], resizing
- forms [Windows Forms], creating resizable
- Windows Forms, resizable
ms.assetid: babdf198-404c-485d-a914-ed370c6ecd99
ms.openlocfilehash: 57c6d30b63b15f5e57e813c1deb90d3da5a5ba35
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705718"
---
# <a name="how-to-create-a-resizable-windows-form-for-data-entry"></a>Практическое руководство. Создание переменного размера Windows формы для ввода данных
Удачно сконструированный макет должен реагировать на изменение размеров родительской формы. Для согласованного изменения размера и положения элементов управления на макете формы при изменении размеров формы можно использовать элемент управления <xref:System.Windows.Forms.TableLayoutPanel>. Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> также полезен в случаях, когда изменение содержимого элементов управления приводит к изменению макета. Процесс, описанный в этой процедуре, можно выполнить в среде Visual Studio.  Также см. в разделе [Пошаговое руководство: Создание переменного размера Windows формы для ввода данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100)).  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование элемента управления <xref:System.Windows.Forms.TableLayoutPanel> для построения макета, который соответствующим образом меняется при изменении пользователем размера формы. Он также демонстрирует, как макет учитывает будущую локализацию.  
  
 [!code-cpp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/cpp/basicdataentryform.cpp#1)]
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/CS/basicdataentryform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.DataEntryForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.DataEntryForm/VB/basicdataentryform.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Практическое руководство. Разработка макета формы Windows, с учетом будущей локализации](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [Взаимодействие с пользователем в Microsoft Windows, официальные рекомендации для разработчиков и конструкторов пользовательских интерфейсов. Редмонд, штат Вашингтон: Microsoft Press, 1999. (USBN: 0-7356-0566-1)](https://www.microsoft.com/mspress/southpacific/books/book11588.htm)
