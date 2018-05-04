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
ms.openlocfilehash: 16f878abc11589fe62f78d941b367d82d7b49e1c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a>Метод WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)
[Поддерживается в .NET Framework 4.5.1 и более поздних версиях.]  
  
 Преобразует заданный поток в поток прямого доступа.  
  
 **Пространство имен:** <xref:System.IO?displayProperty=nameWithType>  
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
