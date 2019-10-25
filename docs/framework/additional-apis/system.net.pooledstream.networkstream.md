---
title: Свойство Пуледстреам. NetworkStream (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 541b8c94b30675c1286b48a2291c3bd3e4aeea0b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847232"
---
# <a name="pooledstreamnetworkstream-property"></a>Пуледстреам. NetworkStream, свойство

Возвращает или задает сетевой поток для сокета `PooledStream`.

## <a name="syntax"></a>Синтаксис

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a>Значение свойства

<xref:System.Net.Sockets.NetworkStream>  
Сетевой поток для сокета `PooledStream`.

## <a name="remarks"></a>Заметки

> [!WARNING]
> Свойство `PooledStream.NetworkStream` является внутренним и не предназначено для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System. dll)

**.NET Framework версии:** Доступно с 2,0.
