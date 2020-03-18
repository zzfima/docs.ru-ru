---
ms.openlocfilehash: 44cb833fc93caaa79000147421e1c013f755b9cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "68238027"
---
### <a name="listboxitem-isselected-binding-issue-with-observablecollectionlttgtmove"></a>Проблема с привязкой ListBoxItem IsSelected к ObservableCollection&lt;T&gt;.Move

|   |   |
|---|---|
|Подробнее|Вызов <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)> или <xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)> для коллекции, привязанной к <xref:System.Windows.Controls.ListBox?displayProperty=name> с выделенными элементами, может привести к последующему выделению или отмене выделения элементов <xref:System.Windows.Controls.ListBox?displayProperty=name>.|
|Предложение|Чтобы обойти эту проблему, выполните вызов <xref:System.Collections.ObjectModel.Collection%601.Remove(%600)?displayProperty=name> и <xref:System.Collections.ObjectModel.Collection%601.Insert(System.Int32,%600)?displayProperty=name> вместо <xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)>. Кроме того, эта проблема была устранена в .NET Framework 4.6 и может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Дополнительный номер|
|Version|4,5|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Collections.ObjectModel.ObservableCollection%601.Move(System.Int32,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.ObjectModel.ObservableCollection%601.MoveItem(System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
