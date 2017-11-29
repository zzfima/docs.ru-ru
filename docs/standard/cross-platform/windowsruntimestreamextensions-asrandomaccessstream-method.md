---
title: "Метод WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
api_name: System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location: System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be93ddc0f3bf0a5079f31bfa0ff5caa882342c37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a><span data-ttu-id="c0a2f-102">Метод WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)</span><span class="sxs-lookup"><span data-stu-id="c0a2f-102">WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) Method</span></span>
<span data-ttu-id="c0a2f-103">[Поддерживается в .NET Framework 4.5.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="c0a2f-103">[Supported in the .NET Framework 4.5.1 and later versions]</span></span>  
  
 <span data-ttu-id="c0a2f-104">Преобразует заданный поток в поток прямого доступа.</span><span class="sxs-lookup"><span data-stu-id="c0a2f-104">Converts the specified stream to a random access stream.</span></span>  
  
 <span data-ttu-id="c0a2f-105">**Пространство имен:**<xref:System.IO?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c0a2f-105">**Namespace:** <xref:System.IO?displayProperty=nameWithType></span></span>  
 <span data-ttu-id="c0a2f-106">**Сборка:** System.Runtime.WindowsRuntime (в System.Runtime.WindowsRuntime.dll)</span><span class="sxs-lookup"><span data-stu-id="c0a2f-106">**Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a2f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0a2f-107">Syntax</span></span>  
  
```csharp  
[CLSCompliantAttribute(false)]  
public static  IRandomAccessStream AsRandomAccessStream(Stream stream)  
```  
  
```vb  
'Declaration  
<ExtensionAttribute> _  
<CLSCompliantAttribute(False)> _  
Public Shared Function AsRandomAccessStream ( _  
        stream As Stream) As IRandomAccessStream  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0a2f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0a2f-108">Parameters</span></span>  
 `stream`  
  
 <span data-ttu-id="c0a2f-109">Тип: <xref:System.IO.Stream?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c0a2f-109">Type: <xref:System.IO.Stream?displayProperty=nameWithType></span></span>  
<span data-ttu-id="c0a2f-110">Поток для преобразования.</span><span class="sxs-lookup"><span data-stu-id="c0a2f-110">The stream to convert.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0a2f-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c0a2f-111">Return Value</span></span>  
 <span data-ttu-id="c0a2f-112">Тип: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span><span class="sxs-lookup"><span data-stu-id="c0a2f-112">Type: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)</span></span>  
<span data-ttu-id="c0a2f-113">Объект [!INCLUDE[wrt](../../../includes/wrt-md.md)] поток прямого доступа, который представляет собой преобразованный поток.</span><span class="sxs-lookup"><span data-stu-id="c0a2f-113">A [!INCLUDE[wrt](../../../includes/wrt-md.md)] random access stream, which represents the converted stream.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="c0a2f-114">Исключения</span><span class="sxs-lookup"><span data-stu-id="c0a2f-114">Exceptions</span></span>  
  
|<span data-ttu-id="c0a2f-115">Исключение</span><span class="sxs-lookup"><span data-stu-id="c0a2f-115">Exception</span></span>|<span data-ttu-id="c0a2f-116">Условие</span><span class="sxs-lookup"><span data-stu-id="c0a2f-116">Condition</span></span>|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|<span data-ttu-id="c0a2f-117">Преобразуемый поток не поддерживает поиск.</span><span class="sxs-lookup"><span data-stu-id="c0a2f-117">The stream to convert does not support seeking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0a2f-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="c0a2f-118">Remarks</span></span>  
 <span data-ttu-id="c0a2f-119">Этот метод расширения доступен только при разработке приложений Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="c0a2f-119">This extension method is available only when you develop Windows Store apps.</span></span> <span data-ttu-id="c0a2f-120">Этот метод обеспечивает удобный способ работы с потоками в приложениях Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="c0a2f-120">This method provides a convenient way of working with streams in Windows Store apps.</span></span> <span data-ttu-id="c0a2f-121">Поток .NET Framework, который нужно преобразовать, должен поддерживать поиск.</span><span class="sxs-lookup"><span data-stu-id="c0a2f-121">The .NET Framework stream you want to convert must support seeking.</span></span> <span data-ttu-id="c0a2f-122">Дополнительные сведения см. в описании метода <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c0a2f-122">For more information, see the <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0a2f-123">Этот API поддерживается в платформе .NET Framework 4.5.1 и более поздних версиях, но не в версии 4.5.</span><span class="sxs-lookup"><span data-stu-id="c0a2f-123">This API is supported in the .NET Framework 4.5.1 and later versions, but not in version 4.5.</span></span>  
  
## <a name="version-information"></a><span data-ttu-id="c0a2f-124">Сведения о версии</span><span class="sxs-lookup"><span data-stu-id="c0a2f-124">Version Information</span></span>  
 <span data-ttu-id="c0a2f-125">**Приложения .NET для магазина Windows**</span><span class="sxs-lookup"><span data-stu-id="c0a2f-125">**.NET for Windows Store apps**</span></span>  
  
 <span data-ttu-id="c0a2f-126">Поддерживается в Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c0a2f-126">Supported in: Windows 8.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0a2f-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c0a2f-127">See Also</span></span>  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [<span data-ttu-id="c0a2f-128">Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="c0a2f-128">How to: Convert Between .NET Framework Streams and Windows Runtime Streams</span></span>](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
