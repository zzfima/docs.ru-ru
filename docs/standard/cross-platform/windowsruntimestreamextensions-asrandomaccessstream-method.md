---
title: Метод WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a712414163446606cbc93154bc821d3b1166fe8f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561800"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="ce2b4-102">Метод WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)</span><span class="sxs-lookup"><span data-stu-id="ce2b4-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>

<span data-ttu-id="ce2b4-103">[Поддерживается в .NET Framework 4.5.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="ce2b4-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>

<span data-ttu-id="ce2b4-104">Преобразует заданный поток в поток прямого доступа.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-104">Converts the specified stream to a random access stream.</span></span>

<span data-ttu-id="ce2b4-105">**Пространство имен:** <xref:System.IO?displayProperty=nameWithType> 
 **сборки:** System.Runtime.WindowsRuntime (в System.Runtime.WindowsRuntime.dll)</span><span class="sxs-lookup"><span data-stu-id="ce2b4-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType>
**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>

## <a name="syntax"></a><span data-ttu-id="ce2b4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce2b4-106">Syntax</span></span>

```csharp
[CLSCompliantAttribute(false)]
public static IRandomAccessStream AsRandomAccessStream(Stream stream)
```

```vb
'Declaration
<ExtensionAttribute> _
<CLSCompliantAttribute(False)> _
Public Shared Function AsRandomAccessStream ( _
        stream As Stream) As IRandomAccessStream
```

## <a name="parameters"></a><span data-ttu-id="ce2b4-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce2b4-107">Parameters</span></span>

`stream`

<span data-ttu-id="ce2b4-108">Тип: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ce2b4-108">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="ce2b4-109">Поток для преобразования.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-109">The stream to convert.</span></span>

## <a name="return-value"></a><span data-ttu-id="ce2b4-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ce2b4-110">Return Value</span></span>

<span data-ttu-id="ce2b4-111">Тип: <xref:Windows.Storage.Streams.RandomAccessStream></span><span class="sxs-lookup"><span data-stu-id="ce2b4-111">Type: <xref:Windows.Storage.Streams.RandomAccessStream></span></span>  
<span data-ttu-id="ce2b4-112">Объект [!INCLUDE[wrt](../../../includes/wrt-md.md)] поток прямого доступа, которая представляет преобразованный поток.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-112">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>

## <a name="exceptions"></a><span data-ttu-id="ce2b4-113">Исключения</span><span class="sxs-lookup"><span data-stu-id="ce2b4-113">Exceptions</span></span>

|<span data-ttu-id="ce2b4-114">Исключение</span><span class="sxs-lookup"><span data-stu-id="ce2b4-114">Exception</span></span>|<span data-ttu-id="ce2b4-115">Условие</span><span class="sxs-lookup"><span data-stu-id="ce2b4-115">Condition</span></span>|
|---------------|---------------|
|<xref:System.NotSupportedException>|<span data-ttu-id="ce2b4-116">Преобразуемый поток не поддерживает поиск.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-116">The stream to convert does not support seeking.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ce2b4-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce2b4-117">Remarks</span></span>

<span data-ttu-id="ce2b4-118">Этот метод расширения доступен только при разработке приложений Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-118">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="ce2b4-119">Этот метод обеспечивает удобный способ работы с потоками в приложениях Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-119">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="ce2b4-120">Поток .NET Framework, который нужно преобразовать, должен поддерживать поиск.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-120">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="ce2b4-121">Дополнительные сведения см. в описании метода <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-121">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce2b4-122">Этот API поддерживается в платформе .NET Framework 4.5.1 и более поздних версиях, но не в версии 4.5.</span><span class="sxs-lookup"><span data-stu-id="ce2b4-122">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>

## <a name="version-information"></a><span data-ttu-id="ce2b4-123">Сведения о версии</span><span class="sxs-lookup"><span data-stu-id="ce2b4-123">Version Information</span></span>

<span data-ttu-id="ce2b4-124">**.NET для приложений Windows Store**</span><span class="sxs-lookup"><span data-stu-id="ce2b4-124">**.NET for Windows Store apps**</span></span>

<span data-ttu-id="ce2b4-125">Поддерживается в Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ce2b4-125">Supported in: Windows 8.1</span></span>

## <a name="see-also"></a><span data-ttu-id="ce2b4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ce2b4-126">See Also</span></span>

<span data-ttu-id="ce2b4-127">[System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx)</span><span class="sxs-lookup"><span data-stu-id="ce2b4-127">[System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions(v=vs.110).aspx)</span></span>  
[<span data-ttu-id="ce2b4-128">Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="ce2b4-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  