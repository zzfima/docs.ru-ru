---
ms.openlocfilehash: 82835915efa0e113e81bb09bd5062ee3252f2a64
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568120"
---
### <a name="invalidasynchronousstateexception-moved-to-another-assembly"></a>Исключение InvalidAsynchronousStateException перенесено в другую сборку

Класс <xref:System.ComponentModel.InvalidAsynchronousStateException> перемещен.

#### <a name="change-description"></a>Описание изменений

В .NET Core 2.2 и более ранних версиях класс <xref:System.ComponentModel.InvalidAsynchronousStateException> находится в сборке *System.ComponentModel.TypeConverter*.

Начиная с .NET Core 3.0, он находится в сборке *System.ComponentModel.Primitives*.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="recommended-action"></a>Рекомендуемое действие

Это изменение влияет только на приложения, использующие отражение для загрузки <xref:System.ComponentModel.InvalidAsynchronousStateException> путем вызова метода, такого как <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>, или перегрузки <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>, которая предполагает, что тип находится в определенной сборке. В этом случае сборку, указанную в вызове метода, необходимо обновить в соответствии с новым расположением сборки типа.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- Нет

<!--

### Affected APIs

- Not detectable via API analysis

-->
