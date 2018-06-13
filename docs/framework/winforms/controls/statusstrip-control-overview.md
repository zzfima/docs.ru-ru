---
title: Общие сведения об элементе управления StatusStrip
ms.date: 03/30/2017
f1_keywords:
- StatusStrip
helpviewer_keywords:
- StatusStrip control [Windows Forms], about StatusStrip control
- status bars [Windows Forms], about status bars
ms.assetid: c0d9bcbb-f8b8-46ef-bae2-4146b8c8ce99
ms.openlocfilehash: b915be2db6865a95d2d37afda58983dbb2edca27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537912"
---
# <a name="statusstrip-control-overview"></a>Общие сведения об элементе управления StatusStrip
Элемент управления <xref:System.Windows.Forms.StatusStrip> отображает сведения об объекте, который просматривается в <xref:System.Windows.Forms.Form>, компонентах объекта или информации о контексте, относящиеся к работе объекта внутри приложения. Как правило, элемент управления <xref:System.Windows.Forms.StatusStrip> состоит из объектов <xref:System.Windows.Forms.ToolStripStatusLabel>, каждый из которых отображает текст, значок, либо и текст и значок. <xref:System.Windows.Forms.StatusStrip> также могут содержать элементы управления <xref:System.Windows.Forms.ToolStripDropDownButton>, <xref:System.Windows.Forms.ToolStripSplitButton> и <xref:System.Windows.Forms.ToolStripProgressBar>.  
  
 По умолчанию в <xref:System.Windows.Forms.StatusStrip> панели отсутствуют. Чтобы добавить панели в <xref:System.Windows.Forms.StatusStrip>, используйте метод <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A?displayProperty=nameWithType>.  
  
 Существует расширенная поддержка обработки элементов <xref:System.Windows.Forms.StatusStrip> и общих команд в Visual Studio.  
  
 См. также [редактор коллекции элементов StatusStrip](http://msdn.microsoft.com/library/ms233631\(v=vs.110\)), [диалоговое окно задач StatusStrip](http://msdn.microsoft.com/library/ms233642\(v=vs.110\)).  
  
 Хотя <xref:System.Windows.Forms.StatusStrip> заменяет и расширяет элемент управления <xref:System.Windows.Forms.StatusBar> предыдущих версий, <xref:System.Windows.Forms.StatusBar> сохраняется для обеспечения обратной совместимости и использования в будущем при его выборе.  
  
### <a name="important-statusstrip-members"></a>Важные члены StatusStrip  
  
|Имя|Описание|  
|----------|-----------------|  
|<xref:System.Windows.Forms.StatusStrip.CanOverflow%2A>|Возвращает или задает значение, которое указывает, поддерживает ли <xref:System.Windows.Forms.StatusStrip> область переполнения.|  
|<xref:System.Windows.Forms.StatusStrip.Stretch%2A>|Возвращает или задает значение, которое указывает, растягивается ли элемент управления <xref:System.Windows.Forms.StatusStrip> во всю длину в своем контейнере <xref:System.Windows.Forms.ToolStripContainer>.|  
  
### <a name="important-statusstrip-companion-classes"></a>Важные сопутствующие классы StatusStrip  
  
|Имя|Описание|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|Представляет панель элемента управления <xref:System.Windows.Forms.StatusStrip>.|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Отображает связанный <xref:System.Windows.Forms.ToolStripDropDown>, из которого пользователь может выбрать единичный элемент.|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|Представляет элемент управления, состоящий из двух частей, которые являются обычной кнопкой и раскрывающимся меню.|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|Отображает состояние завершения процесса.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>
