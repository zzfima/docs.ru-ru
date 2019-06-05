---
ms.openlocfilehash: 53fc2a51a7995e9b6ad43e28429313d2aea9abf1
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66379233"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-result-in-an-unresponsive-application"></a>Прокрутка TreeView в WPF или сгруппированный ListBox в VirtualizingStackPanel может привести к зависанию приложения

|   |   |
|---|---|
|Подробные сведения|В версии .NET Framework 4.5 прокрутка <xref:System.Windows.Controls.TreeView?displayProperty=name> WPF на панели виртуализированного стека может привести к зависанию приложения при наличии полей в области просмотра (между элементами в <xref:System.Windows.Controls.TreeView?displayProperty=name>, например, или в элементе ItemsPresenter). Кроме того, в некоторых случаях элементы разных размеров в представлении могут привести к нестабильности даже при отсутствии полей.|
|Предложение|Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1. Кроме того, можно удалить поля из коллекций представлений (таких как <xref:System.Windows.Controls.TreeView?displayProperty=name>) на панелях виртуализированных стеков, если все содержащиеся в них элементы имеют одинаковый размер.|
|Область|Значительно|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
