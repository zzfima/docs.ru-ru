---
title: Разработка макета, ориентированного на локализацию
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: 36ffd532b9f539107307144d25c8d9d5f8ba634a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743281"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>Практическое руководство. Формирование макета формы Windows Forms с учетом будущей локализации
Создание готовых для локализации форм значительно ускоряет разработку продуктов для международных рынков. Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> можно использовать для реализации макетов, которые поддерживают изменение размера элементов управления при изменении значений их свойств <xref:System.Windows.Forms.Control.Text%2A>.  
  
## <a name="example"></a>Пример  
 Эта форма показывает, как создать макет, который пропорционально корректируется при отображении строковых значений на других языках. Такой процесс перевода называется *локализацией*. Подробнее об этом см. в разделе [Локализация](../../../standard/globalization-localization/localization.md).  
  
 В Visual Studio предусмотрена расширенная поддержка данной задачи.  См. также раздел [Пошаговое руководство. Создание структуры, сохраняющей пропорции при локализации](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a>Дополнительные ресурсы

1. [Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize](windows-forms-controls-padding-autosize.md)  
  
8. [Практическое руководство. Обеспечение поддержки локализации в Windows Forms с помощью элементов управления AutoSize и TableLayoutPanel](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))  
  
9. [Пошаговое руководство. Создание в Windows Forms формы для ввода данных переменного размера](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [Локализация](../../../standard/globalization-localization/localization.md)
