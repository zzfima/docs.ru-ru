---
ms.openlocfilehash: 4d479636f41095610eaf39f92ad0dad4863ab8b5
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568236"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a>Класс TypeDescriptionProviderAttribute перенесен в другую сборку

Класс <xref:System.ComponentModel.TypeDescriptionProviderAttribute> перемещен.

#### <a name="change-description"></a>Описание изменений

В .NET Core 2.2 и более ранних версиях класс <xref:System.ComponentModel.TypeDescriptionProviderAttribute> находится в сборке *System.ComponentModel.TypeConverter*.

Начиная с .NET Core 3.0 он находится в сборке *System.ObjectModel*.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

Это изменение влияет только на приложения, использующие отражение для загрузки типа <xref:System.ComponentModel.TypeDescriptionProviderAttribute> путем вызова метода, такого как <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, или перегрузки <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>, которая предполагает, что тип находится в определенной сборке. В этом случае сборку, указанную в вызове метода, необходимо обновить в соответствии с новым расположением сборки типа.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- Нет

<!--

### Affected APIs

- Not detectable via API analysis

-->
