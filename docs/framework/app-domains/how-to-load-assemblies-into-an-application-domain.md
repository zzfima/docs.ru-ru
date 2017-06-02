---
title: "Практическое руководство. Загрузка сборок в домен приложения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "домены приложений, загрузка сборок"
  - "загрузка сборок"
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Загрузка сборок в домен приложения
Существует несколько способов загрузки сборки в домен приложения.  Рекомендуется использование `static` \(`Shared` в Visual Basic\) метода <xref:System.Reflection.Assembly.Load%2A> класса [System.Reflection.Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx).  Другими способами загрузки сборок являются:  
  
-   Метод <xref:System.Reflection.Assembly.LoadFrom%2A> класса [Assembly](https://msdn.microsoft.com/en-us/library/system.reflection.aspx) загружает сборку, заданную расположением ее файла.  При загрузке сборок с помощью этого метода используется другой контекст загрузки.  
  
-   Методы <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> и <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> загружают сборку в контекст, предназначенный только для отражения.  Сборки, загруженные в этом контексте, могут быть проверены, но не выполнены, позволяя производить проверку сборок, предназначенных для других платформ.  См. раздел [How to: Load Assemblies into the Reflection\-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).  
  
> [!NOTE]
>  Контекст только для отражения впервые появился в платформе .NET Framework версии 2.0.  
  
-   Такие методы, как <xref:System.AppDomain.CreateInstance%2A> и <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> класса <xref:System.AppDomain> могут загружать сборки в домен приложения.  
  
-   Метод <xref:System.Type.GetType%2A> класса <xref:System.Type> может загружать сборки.  
  
-   Метод <xref:System.AppDomain.Load%2A> класса <xref:System.AppDomain?displayProperty=fullName> может загружать сборки, но используется он главным образом для COM\-взаимодействия.  Его не следует использовать для загрузки сборок в домен приложения, отличный от домена приложения, из которого он вызывается.  
  
> [!NOTE]
>  Начиная с платформы .NET Framework версии 2.0, среда выполнения не загружает сборки, которые были скомпилированы версиями платформы .NET Framework, чей номер версии выше, чем у текущей среды выполнения.  Это относится к сочетанию основных и дополнительных номеров версии.  
  
 Можно определить способ, которым JIT\-скомпилированный код из загруженных сборок будет распределен между доменами приложений.  Для получения дополнительной информации см. [Application Domains and Assemblies](http://msdn.microsoft.com/ru-ru/433b04ae-4ba8-4849-9dbd-79194f240346).  
  
## Пример  
 Следующий код загружает сборку с именем "example.exe" или "Example.dll" в текущий домен приложения, получает тип с именем `Example` из сборки, получает метод без параметров `MethodA` для этого типа и выполняет этот метод.  Полное описание получения сведений из загруженной сборки см. в разделе [Динамическая загрузка и использование типов](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md).  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## См. также  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>   
 [Hosting Overview](http://msdn.microsoft.com/ru-ru/ea527626-99e3-4995-81c4-c8f3e60eb6d5)   
 [Programming with Application Domains](http://msdn.microsoft.com/ru-ru/bd36055b-56bd-43eb-b4d8-820c37172131)   
 [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)   
 [Использование доменов приложений](../../../docs/framework/app-domains/use.md)   
 [How to: Load Assemblies into the Reflection\-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)   
 [Application Domains and Assemblies](http://msdn.microsoft.com/ru-ru/433b04ae-4ba8-4849-9dbd-79194f240346)