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
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a>Метод WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)
[Поддерживается в .NET Framework 4.5.1 и более поздних версиях.]  
  
 Преобразует заданный поток в поток прямого доступа.  
  
 **Пространство имен:**<xref:System.IO?displayProperty=nameWithType>  
 **Сборка:** System.Runtime.WindowsRuntime (в System.Runtime.WindowsRuntime.dll)  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `stream`  
  
 Тип: <xref:System.IO.Stream?displayProperty=nameWithType>  
Поток для преобразования.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Тип: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)  
Объект [!INCLUDE[wrt](../../../includes/wrt-md.md)] поток прямого доступа, который представляет собой преобразованный поток.  
  
## <a name="exceptions"></a>Исключения  
  
|Исключение|Условие|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|Преобразуемый поток не поддерживает поиск.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод расширения доступен только при разработке приложений Магазина Windows. Этот метод обеспечивает удобный способ работы с потоками в приложениях Магазина Windows. Поток .NET Framework, который нужно преобразовать, должен поддерживать поиск. Дополнительные сведения см. в описании метода <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Этот API поддерживается в платформе .NET Framework 4.5.1 и более поздних версиях, но не в версии 4.5.  
  
## <a name="version-information"></a>Сведения о версии  
 **Приложения .NET для магазина Windows**  
  
 Поддерживается в Windows 8.1  
  
## <a name="see-also"></a>См. также  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
