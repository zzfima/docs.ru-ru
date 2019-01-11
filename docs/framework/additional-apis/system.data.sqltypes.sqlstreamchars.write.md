---
title: Метод SqlStreamChars.Write (Char [], Int32, Int32) (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.Write
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: dd9bb691f6d07f4875d684eef76d6329667003af
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221912"
---
# <a name="sqlstreamcharswritechar-int32-int32-method"></a><span data-ttu-id="0023c-102">Метод SqlStreamChars.Write (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="0023c-102">SqlStreamChars.Write(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="0023c-103">При переопределении в производном классе, записывает последовательность символов в текущий поток и перемещает текущую позицию внутри потока на число записанных символов.</span><span class="sxs-lookup"><span data-stu-id="0023c-103">When overridden in a derived class, writes a sequence of characters to the current stream and advances the current position within this stream by the number of characters written.</span></span> <span data-ttu-id="0023c-104">Дружественные сборки, содержащей этот метод связан с SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="0023c-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="0023c-105">Он предназначен для использования с SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0023c-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="0023c-106">Для других баз данных используйте механизм размещения, предоставляемый этой базы данных.</span><span class="sxs-lookup"><span data-stu-id="0023c-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract void Write (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="0023c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0023c-107">Parameters</span></span>

`buffer`  
<span data-ttu-id="0023c-108">Записываемый массив char.</span><span class="sxs-lookup"><span data-stu-id="0023c-108">A char array to write.</span></span>

`offset`  
<span data-ttu-id="0023c-109">Смещение относительно начала координат.</span><span class="sxs-lookup"><span data-stu-id="0023c-109">An offset relative to origin.</span></span>

`count`  
<span data-ttu-id="0023c-110">Число символов для записи в текущий поток.</span><span class="sxs-lookup"><span data-stu-id="0023c-110">The number of characters to be written to the current stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="0023c-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="0023c-111">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0023c-112">`SqlStreamChars.Write` Метод является закрытым и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="0023c-112">The `SqlStreamChars.Write` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0023c-113">Майкрософт не поддерживает использование этого поля в рабочем приложении ни при каких обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="0023c-113">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0023c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0023c-114">Requirements</span></span>

<span data-ttu-id="0023c-115">**Пространство имен:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="0023c-115">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="0023c-116">**Сборка:** System.Data (в System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="0023c-116">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="0023c-117">**Версии платформы .NET framework:** Доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="0023c-117">**.NET Framework versions:** Available since 2.0.</span></span>