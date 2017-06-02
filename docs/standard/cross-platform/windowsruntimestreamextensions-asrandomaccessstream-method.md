---
title: "Метод WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream"
apilocation: 
  - "System.Runtime.WindowsRuntime.dll"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# Метод WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)
\[Поддерживается только в .NET Framework 4.5.1 и более поздних версиях\]  
  
 Преобразует заданный поток в поток прямого доступа.  
  
 **Пространство имен:** <xref:System.IO?displayProperty=fullName>   
 **Сборка:** System.Runtime.WindowsRuntime \(в System.Runtime.WindowsRuntime.dll\)  
  
## Синтаксис  
  
```csharp  
[CLSCompliantAttribute(false)] public static  IRandomAccessStream AsRandomAccessStream(Stream stream)   
```  
  
```vb  
'Declaration <ExtensionAttribute> _ <CLSCompliantAttribute(False)> _ Public Shared Function AsRandomAccessStream ( _         stream As Stream) As IRandomAccessStream   
```  
  
#### Параметры  
 `stream`  
  
 Тип: <xref:System.IO.Stream?displayProperty=fullName>   
 Поток для преобразования.  
  
## Возвращаемое значение  
 Введите: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)   
 Поток прямого доступа [!INCLUDE[wrt](../../../includes/wrt-md.md)], который представляет собой преобразованный поток.  
  
## Исключения  
  
|Исключение|Условие|  
|----------------|-------------|  
|<xref:System.NotSupportedException>|Преобразуемый поток не поддерживает поиск.|  
  
## Примечания  
 Этот метод расширения доступен только при разработке приложений Магазина Windows.  Этот метод обеспечивает удобный способ работы с потоками в приложениях Магазина Windows.  Поток .NET Framework, который нужно преобразовать, должен поддерживать поиск.  Дополнительные сведения см. в описании метода <xref:System.IO.Stream.Seek%2A?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  Этот API поддерживается в платформе .NET Framework 4.5.1 и более поздних версиях, но не в версии 4.5.  
  
## Сведения о версии  
 **.NET для приложений Магазина Windows**  
  
 Поддерживается в Windows 8.1  
  
## См. также  
 <xref:System.IO.WindowsRuntimeStreamExtensions>   
 [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)