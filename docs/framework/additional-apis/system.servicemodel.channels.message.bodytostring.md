---
title: Метод Message. Бодитостринг (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 9f1f852c0bd82299fd40afe66a5f90cd7c0335cf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215507"
---
# <a name="messagebodytostring-method"></a><span data-ttu-id="a09f7-102">Метод Message. Бодитостринг</span><span class="sxs-lookup"><span data-stu-id="a09f7-102">Message.BodyToString Method</span></span>

<span data-ttu-id="a09f7-103">Преобразует текст сообщения в строку путем вызова метода <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a09f7-103">Converts the message body into a string by calling the <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a><span data-ttu-id="a09f7-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="a09f7-104">Parameters</span></span>

- <span data-ttu-id="a09f7-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="a09f7-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="a09f7-106">Модуль записи, используемый для преобразования тела сообщения в строку.</span><span class="sxs-lookup"><span data-stu-id="a09f7-106">The writer that is used to convert the message body to a string.</span></span>

## <a name="remarks"></a><span data-ttu-id="a09f7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a09f7-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="a09f7-108">Метод `Message.BodyToString` является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="a09f7-108">The `Message.BodyToString` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a09f7-109">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="a09f7-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="a09f7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a09f7-110">Requirements</span></span>

<span data-ttu-id="a09f7-111">**Пространство имен:** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="a09f7-111">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="a09f7-112">**Сборка:** System. ServiceModel. dll</span><span class="sxs-lookup"><span data-stu-id="a09f7-112">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="a09f7-113">**.NET Framework версии:** Доступно с 3,0.</span><span class="sxs-lookup"><span data-stu-id="a09f7-113">**.NET Framework versions:** Available since 3.0.</span></span>
