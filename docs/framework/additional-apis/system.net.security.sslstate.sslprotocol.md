---
title: Свойство Сслстате. Сслпротокол (System .NET. Security)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Security.SslState.SslProtocol
- System.Net.Security.SslState.get_SslProtocol
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 6983ac071dad29b240308031ecd0a3562a6856e4
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847250"
---
# <a name="sslstatesslprotocol-property"></a>Сслстате. Сслпротокол, свойство

Возвращает версии протокола SSL.

## <a name="syntax"></a>Синтаксис

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a>Значение свойства

<xref:System.Security.Authentication.SslProtocols>  
Побитовое сочетание значений перечисления, определяющих версии протокола SSL.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Свойство `SslState.SslProtocol` является внутренним и не предназначено для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net.Security>

**Сборка:** Система (в System. dll)

**.NET Framework версии:** Доступно с 2,0.
