---
ms.openlocfilehash: 57ca2ad839aab8d61da1a929660920efe1190334
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147540"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a>Класс TypeDescriptionProviderAttribute перенесен в другую сборку

Класс <xref:System.ComponentModel.TypeDescriptionProviderAttribute> перемещен.

#### <a name="change-description"></a>Описание изменений

В .NET Core 2.2 и более ранних версиях класс <xref:System.ComponentModel.TypeDescriptionProviderAttribute> находится в сборке *System.ComponentModel.TypeConverter*.

Начиная с .NET Core 3.0 он находится в сборке *System.ObjectModel*.

#### <a name="version-introduced"></a>Представленная версия

3,0

#### <a name="recommended-action"></a>Рекомендованное действие

Это изменение влияет только на приложения, использующие отражение для загрузки типа <xref:System.ComponentModel.TypeDescriptionProviderAttribute> путем вызова метода, такого как <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, или перегрузки <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>, которая предполагает, что тип находится в определенной сборке. В этом случае сборку, указанную в вызове метода, необходимо обновить в соответствии с новым расположением сборки типа.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

Нет.

<!--

### Affected APIs

- Not detectable via API analysis

-->
