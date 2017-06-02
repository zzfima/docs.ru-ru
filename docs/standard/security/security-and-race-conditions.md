---
title: "Security and Race Conditions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "security [.NET Framework], race conditions"
  - "race conditions"
  - "secure coding, race conditions"
  - "code security, race conditions"
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Security and Race Conditions
Другой областью, которую следует рассмотреть в связи с возможностью возникновения бреши в безопасности, является конкуренция.  Слабые места в защите могут возникать различными способами.  Нижеследующие подразделы описывают некоторые основные ловушки, которые разработчик должен обойти.  
  
## Состояние гонки в методе Dispose  
 Если метод **Dispose** \(дополнительные сведения см. в разделе [Garbage Collection](../../../docs/standard/garbage-collection/index.md)\) класса не синхронизирован, существует возможность того, что код очистки, находящийся внутри **Dispose**, будет запущен более одного раза, как это показано в следующем примере.  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
  
```  
  
```csharp  
void Dispose()   
{  
    if( myObj != null )   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 Поскольку рассматриваемая реализация метода **Dispose** не является синхронизированной, существует возможность того, что процедура `Cleanup` будет вызвана сначала одним потоком, а затем сразу другим потоком, еще перед присваиванием `_myObj` значения **null**.  Относится ли описанная проблема к обеспечению безопасности или нет, зависит от того, что конкретно происходит при выполнении кода `Cleanup`.  Основная проблема, связанная с несинхронизированными реализациями **Dispose**, относится к использованию дескрипторов ресурсов, например файлов.  Неверное удаление может привести к использованию некорректного дескриптора, что часто создает уязвимые места в системе безопасности.  
  
## Состояния гонки в конструкторах  
 В некоторых приложениях возможна ситуация, когда другие потоки могут получить доступ к членам класса еще перед тем, как будут полностью выполнены конструкторы этого класса.  Необходимо просмотреть все конструкторы класса, чтобы убедиться, что возникновение рассмотренной ситуации не приводит к проблемам с обеспечением безопасности, либо, в случае необходимости, следует синхронизировать потоки.  
  
## Состояние гонки и кэшированные объекты  
 Код, который кэширует важные для обеспечения безопасности данные или использует операцию [Assert](../../../docs/framework/misc/using-the-assert-method.md) системы управления доступом для кода, может также стать уязвимым для конкуренции в случае, если другие составляющие класса не синхронизированы должным образом, как это показано в следующем примере.  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False()  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
  
```  
  
```csharp  
void SomeSecureFunction()   
{  
    if(SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false();  
    }  
}  
void DoOtherWork()   
{  
    if( fCallersOK )   
    {  
        DoSomethingTrusted();  
    }  
    else   
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 Если есть другие пути к `DoOtherWork` и эта процедура может быть вызвана из другого потока с этим же объектом, ненадежный вызывающий объект в состоянии обойти требование системы защиты.  
  
 Если код кэширует важные для обеспечения безопасности данные, убедитесь, что он в достаточной степени защищен.  
  
## Состояния гонки в методах завершения  
 Состояние гонки может также возникать в объекте, который ссылается на статический или неуправляемый ресурс и затем освобождает данный ресурс в своем методе завершения.  Если разные объекты разделяют ресурс, с которым осуществляются какие\-либо действия в методе завершения класса, объекты должны синхронизировать все обращения к данному ресурсу.  
  
## См. также  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)