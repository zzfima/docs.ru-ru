---
title: Практическое руководство. Связывание объекта ContextMenuStrip с элементом управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: 7776a5e5ed6e650aad82f7863a7fa1748006b3bc
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266556"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a>Практическое руководство. Связывание объекта ContextMenuStrip с элементом управления
После создания элементов управления и контекстных меню используйте приведенные ниже процедуры для вывода определенного контекстного меню, когда пользователь щелкает элемент управления правой кнопкой мыши. Эти процедуры связывают объект <xref:System.Windows.Forms.ContextMenuStrip> с формой Windows Forms и элементом управления <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a>Связывание объекта ContextMenuStrip с формой Windows Forms  
  
1.  Присвойте свойству <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> имя связанного объекта <xref:System.Windows.Forms.ContextMenuStrip>.  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a>Связывание объекта ContextMenuStrip с элементом управления ToolStrip  
  
1.  Присвойте свойству <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> элемента управления имя связанного объекта <xref:System.Windows.Forms.ContextMenuStrip>.  
  
## <a name="example"></a>Пример  
 В примере кода ниже создается форма Windows Forms и элемент управления <xref:System.Windows.Forms.ToolStrip>, после чего с ними связывается элемент управления <xref:System.Windows.Forms.ContextMenuStrip>.  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.  
  
 Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>  
 <xref:System.Windows.Forms.ToolStrip>  
 [Практическое руководство. Добавление элементов меню в элемент управления ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)  
 [Элемент управления ContextMenuStrip](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
