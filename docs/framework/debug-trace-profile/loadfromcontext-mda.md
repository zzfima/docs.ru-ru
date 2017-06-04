---
title: "loadFromContext MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MDAs (managed debugging assistants), LoadFrom context"
  - "managed debugging assistants (MDAs), LoadFrom context"
  - "LoadFrom context"
  - "LoadFromContext MDA"
ms.assetid: a9b14db1-d3a9-4150-a767-dcf3aea0071a
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# loadFromContext MDA
Помощник по отладке управляемого кода \(MDA\) `loadFromContext` активируется при загрузке сборки в контекст `LoadFrom`.   Это может произойти в результате вызова метода <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName> или других сходных методов.  
  
## Признаки  
 Использование некоторых методов загрузки может привести к тому, что сборки загружаются в контекст `LoadFrom`.  Использование данного контекста может привести к непредвиденному поведению при сериализации, приведении типов и разрешении зависимостей.  В целом, во избежание подобных проблем рекомендуется загружать сборки в контекст `Load`.  Трудно определить, в какой контекст загружается сборка, если данный помощник по отладке управляемого кода не включен.  
  
## Причина  
 Как правило, сборка загружается в контекст `LoadFrom`, если она была загружена из пути вне контекста `Load`, например из глобального кэша сборки или из свойства <xref:System.AppDomainSetup.ApplicationBase%2A?displayProperty=fullName>.  
  
## Решение  
 Необходимо настроить приложения таким образом, чтобы вызовы метода <xref:System.Reflection.Assembly.LoadFrom%2A> больше не требовались.  Можно использовать для этого следующие методы.  
  
-   Установка сборок в глобальный кэш сборок.  
  
-   Помещение сборок в каталог <xref:System.AppDomainSetup.ApplicationBase%2A> для класса <xref:System.AppDomain>.  В случае с доменом по умолчанию именно в каталоге <xref:System.AppDomainSetup.ApplicationBase%2A> содержится исполняемый файл, который запускает процесс.  Для этого также требуется создание нового класса <xref:System.AppDomain>, если сборку перемещать нежелательно.  
  
-   Добавление проверочного пути к файлу конфигурации приложения \(CONFIG\-файлу\) или во второстепенным доменам приложения, если зависимые сборки находятся в дочерних каталогах, относящихся к исполняемому файлу.  
  
 В каждом конкретном случае код необходимо изменять, чтобы использовать метод <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>.  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду выполнения CLR.  Он только выводит сведения о контексте, который используется в результате запроса загрузки.  
  
## Output  
 Помощник по отладке управляемого кода сообщает о том, что сборка была загружена в контекст `LoadFrom`.  Также помощник по отладке управляемого кода указывает простое имя сборки и путь.  Помощник по отладке управляемого кода также предлагает способы избежать использования контекста `LoadFrom`.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <loadFromContext />  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 В следующем примере кода демонстрируется ситуация, в которой может активироваться данный помощник по отладке управляемого кода:  
  
```  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // The following call caused the LoadFrom context to be used  
            // because the assembly is loaded using LoadFrom and the path is   
            // located outside of the Load context probing path.   
            Assembly.LoadFrom(@"C:\Text\Test.dll");  
        }  
    }  
}  
```  
  
## См. также  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)