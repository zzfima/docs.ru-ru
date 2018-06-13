---
title: Слияние элементов меню в элементе управления MenuStrip в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- MenuStrip [Windows Forms], merging
- merging [Windows Forms], general concepts
ms.assetid: 95e113ba-f362-4dda-8a76-6d95ddc45cee
ms.openlocfilehash: 2782ae483d673f8f1eccab10876aca858737260a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539793"
---
# <a name="merging-menu-items-in-the-windows-forms-menustrip-control"></a>Слияние элементов меню в элементе управления MenuStrip в Windows Forms
Если у вас есть приложения многодокументного интерфейса (MDI), можно объединять пункты меню или целые меню из дочерней формы в меню родительской формы.  
  
 В этом разделе описываются основные понятия, связанные с слияние элементов меню в приложении MDI.  
  
## <a name="general-concepts"></a>Общие понятия  
 Процедуры слияния охватывают целевым объектом и системы управления версиями:  
  
-   Целевой объект — <xref:System.Windows.Forms.MenuStrip> управления на главной или родительской MDI-формы, в которой выполняется слияние пунктов меню.  
  
-   Источником является <xref:System.Windows.Forms.MenuStrip> элемента управления в дочерней форме MDI, содержащий пункты меню, которые требуется объединить с целевым меню.  
  
 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> Свойство идентифицирует элемент меню, список раскрывающегося списка, в которой будет заполнен заголовками MDI текущей родительской дочерние формы MDI. Например, обычно список дочерних окон MDI, открытые в настоящий момент на **окна** меню.  
  
 <xref:System.Windows.Forms.ToolStripMenuItem.IsMdiWindowListEntry%2A> Свойство указано, какие пункты меню берутся из <xref:System.Windows.Forms.MenuStrip> в дочерней форме MDI.  
  
 Пункты меню можно объединить вручную или автоматически. Слияние пунктов меню для обоих методов таким же образом, но включается по-разному, как описано в разделах «Слияние вручную» и «Автоматическое слияние» далее в этом разделе. В процессе ручного и автоматического слияния каждое действие слияния затрагивает следующее.  
  
 <xref:System.Windows.Forms.MenuStrip> пункты меню Слияние перемещаются из одного <xref:System.Windows.Forms.ToolStrip> в другой а не клонируются, как в случае с <xref:System.Windows.Forms.MainMenu>.  
  
## <a name="mergeaction-values"></a>MergeAction значения  
 Задайте действие слияния пунктов меню в источнике <xref:System.Windows.Forms.MenuStrip> с помощью <xref:System.Windows.Forms.MergeAction> свойство.  
  
 В следующей таблице описаны значения и типичные случаи использования доступных операций слияния.  
  
|Значение MergeAction|Описание|Типичные случаи использования|  
|-----------------------|-----------------|-----------------|  
|<xref:System.Windows.Forms.MergeAction.Append>|(По умолчанию) Добавляет исходный элемент в конец коллекции целевого элемента.|Добавление пунктов меню в конец меню при активации определенной части программы.|  
|<xref:System.Windows.Forms.MergeAction.Insert>|Добавляет элемент источника целевого элемента коллекции, в расположении, заданном <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> свойство, заданное для исходного элемента.|Добавление пунктов меню в середину или начало меню при активации определенной части программы.<br /><br /> Если значение <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> одинаково для обоих пунктов меню, они добавляются в обратном порядке. Задать <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> соответствующим образом для сохранения исходного порядка.|  
|<xref:System.Windows.Forms.MergeAction.Replace>|Поиск текстового совпадения или использование <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> значение, если текстовое совпадение не найдено и затем заменяет исходный элемент меню сопоставления целевого элемента меню.|Заменив целевой элемент меню пункта меню источник с таким же именем, действие которого отличается.|  
|<xref:System.Windows.Forms.MergeAction.MatchOnly>|Поиск текстового совпадения или использование <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> значение, если текстовое совпадение не найдено и затем добавляет все элементы раскрывающегося списка из источника в целевой объект.|Построение структуры меню, который вставляет или добавляются в подменю или удаляет элементы меню из вложенного меню. Например, можно добавить элемент меню из дочерней формы MDI в главное <xref:System.Windows.Forms.MenuStrip> **Сохранить как** меню.<br /><br /> <xref:System.Windows.Forms.MergeAction.MatchOnly> позволяет перемещаться по структуре меню без выполнения действий. Он предоставляет способ оценки последующих элементов.|  
|<xref:System.Windows.Forms.MergeAction.Remove>|Поиск текстового совпадения или использование <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> значение, если текстовое совпадение не найдено и затем удаляет элемент из целевого объекта.|Удаление пункта меню из целевого <xref:System.Windows.Forms.MenuStrip>.|  
  
## <a name="manual-merging"></a>Слияние вручную  
 Только <xref:System.Windows.Forms.MenuStrip> элементы управления участвовать в процессе автоматического слияния. Для объединения элементов для других элементов, таких как <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.StatusStrip> элементов управления, слияние нужно выполнить вручную, путем вызова <xref:System.Windows.Forms.ToolStripManager.Merge%2A> и <xref:System.Windows.Forms.ToolStripManager.RevertMerge%2A> методы в коде, при необходимости.  
  
## <a name="automatic-merging"></a>Автоматическое слияние  
 Можно использовать автоматическое слияние для приложений MDI путем активации исходной формы. Для использования <xref:System.Windows.Forms.MenuStrip> в приложении MDI, задайте <xref:System.Windows.Forms.Form.MainMenuStrip%2A> свойство в целевой объект <xref:System.Windows.Forms.MenuStrip> , чтобы операции слияния, выполняемых в источнике <xref:System.Windows.Forms.MenuStrip> отражаются в целевом <xref:System.Windows.Forms.MenuStrip>.  
  
 Автоматическое слияние путем активации можно вызвать <xref:System.Windows.Forms.MenuStrip> в источнике MDI. После активации источника <xref:System.Windows.Forms.MenuStrip> сливается с целевой формой MDI. Когда новая форма становится активным, слияние отменяется на последней формы и запущено на новую форму. Можно контролировать это поведение, задав <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> свойства при необходимости на каждом <xref:System.Windows.Forms.ToolStripItem>и задав <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> свойства на каждом <xref:System.Windows.Forms.MenuStrip>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 [Элемент управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Практическое руководство. Создание списка в окне интерфейса MDI с помощью MenuStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md)  
 [Практическое руководство. Автоматическое слияние меню в приложениях MDI](../../../../docs/framework/winforms/controls/how-to-set-up-automatic-menu-merging-for-mdi-applications.md)
