---
ms.openlocfilehash: 778b6973b0a08e89471f9a4aa31a077da2d30c16
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858368"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>Проблема с привязкой ListBoxItem IsSelected к ObservableCollection&lt;T&gt;.Move

|   |   |
|---|---|
|Подробные сведения|Вызов <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> или <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> для коллекции, привязанной к <xref:System.Windows.Controls.ListBox?displayProperty=name> с выделенными элементами, может привести к последующему выделению или отмене выделения элементов <xref:System.Windows.Controls.ListBox?displayProperty=name>.|
|Предложение|Чтобы обойти эту проблему, выполните вызов <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=name> и <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=name> вместо <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)>. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|

