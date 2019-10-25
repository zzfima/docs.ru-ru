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
# <a name="sslstatesslprotocol-property"></a><span data-ttu-id="f6b05-102">Сслстате. Сслпротокол, свойство</span><span class="sxs-lookup"><span data-stu-id="f6b05-102">SslState.SslProtocol Property</span></span>

<span data-ttu-id="f6b05-103">Возвращает версии протокола SSL.</span><span class="sxs-lookup"><span data-stu-id="f6b05-103">Gets the SSL protocol versions.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6b05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6b05-104">Syntax</span></span>

```csharp
internal SslProtocols SslProtocol { get; }
```

## <a name="property-value"></a><span data-ttu-id="f6b05-105">Значение свойства</span><span class="sxs-lookup"><span data-stu-id="f6b05-105">Property value</span></span>

<xref:System.Security.Authentication.SslProtocols>  
<span data-ttu-id="f6b05-106">Побитовое сочетание значений перечисления, определяющих версии протокола SSL.</span><span class="sxs-lookup"><span data-stu-id="f6b05-106">A bitwise combination of the enumeration values that specify the SSL protocol versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6b05-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="f6b05-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f6b05-108">Свойство `SslState.SslProtocol` является внутренним и не предназначено для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="f6b05-108">The `SslState.SslProtocol` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="f6b05-109">Корпорация Майкрософт не поддерживает использование этого свойства в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="f6b05-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="f6b05-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f6b05-110">Requirements</span></span>

<span data-ttu-id="f6b05-111">**Пространство имен:** <xref:System.Net.Security></span><span class="sxs-lookup"><span data-stu-id="f6b05-111">**Namespace:** <xref:System.Net.Security></span></span>

<span data-ttu-id="f6b05-112">**Сборка:** Система (в System. dll)</span><span class="sxs-lookup"><span data-stu-id="f6b05-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="f6b05-113">**.NET Framework версии:** Доступно с 2,0.</span><span class="sxs-lookup"><span data-stu-id="f6b05-113">**.NET Framework versions:** Available since 2.0.</span></span>
