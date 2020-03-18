---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449413"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes

В .NET Core <xref:System.UnauthorizedAccessException> возникает, когда вызывающий пытается задать значение атрибута файла, но у него нет разрешений на запись.

#### <a name="change-description"></a>Описание изменений

В .NET Framework <xref:System.ArgumentException> возникает, когда вызывающий пытается задать значение атрибута файла в <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>, но у него нет разрешений на запись. В .NET Core вместо него возникает <xref:System.UnauthorizedAccessException> (в .NET Core <xref:System.ArgumentException> по-прежнему возникает, если вызывающий пытается задать недопустимый атрибут файла).

#### <a name="version-introduced"></a>Представленная версия

1,0

#### <a name="recommended-action"></a>Рекомендованное действие

Изменяйте любые инструкции `catch`, чтобы получить <xref:System.UnauthorizedAccessException> вместо или в дополнение к <xref:System.ArgumentException> по мере необходимости.

#### <a name="category"></a>Категория

CoreFX

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
