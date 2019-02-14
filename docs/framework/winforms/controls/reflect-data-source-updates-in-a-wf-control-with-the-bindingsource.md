---
title: Как выполнить  Отражение обновились в источнике данных в элементе управления Windows Forms с использованием компонента BindingSource
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: fca356c258b482a9f4e4fd64f48801de428f8426
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260833"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a>Как выполнить  Отражение обновились в источнике данных в элементе управления Windows Forms с использованием компонента BindingSource
При использовании элементов управления с привязкой к данным иногда необходимо реагировать на изменения в источнике данных, если источник данных не вызывает события изменения списка. При использовании компонента <xref:System.Windows.Forms.BindingSource> для привязки источника данных к элементу управления Windows Forms можно уведомить элемент управления об изменении источника данных путем вызова метода <xref:System.Windows.Forms.BindingSource.ResetBindings%2A>.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано использование метода <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> для уведомления связанного элемента управления об изменении в источнике данных.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Drawing и System.Windows.Forms.  
  
 Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Компонент BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [Практическое руководство. Привязка элемента управления Windows Forms к типу](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
