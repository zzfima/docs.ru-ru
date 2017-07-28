---
title: "bindingFailure MDA | Microsoft Docs"
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
  - "binding failure"
  - "binding, failures"
  - "MDAs (managed debugging assistants), binding failures"
  - "assemblies [.NET Framework], binding failures"
  - "managed debugging assistants (MDAs), binding failures"
  - "BindingFailure MDA"
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# bindingFailure MDA
Управляемый помощник по отладке \(MDA\) `bindingFailure` активируется при неудачной загрузке сборки.  
  
## Признаки  
 Код совершил попытку загрузки сборки с помощью статической ссылки или одного из методов загрузки, например, <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> или <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>.  Сборка не загружается и возникает исключение <xref:System.IO.FileNotFoundException> или <xref:System.IO.FileLoadException>.  
  
## Причина  
 Ошибка привязки возникает, когда среде выполнения не удается загрузить сборку.  Ошибка привязки может возникнуть в результате одной из следующих ситуаций:  
  
-   Среде CLR не удается найти запрошенную сборку.  Это может произойти по многим причинам, например, если сборка не была установлена, или если приложение неверно настроено и не может найти сборку.  
  
-   Как правило, проблема возникает в результате передачи типа другому домену приложения, который требует, чтобы среда CLR загрузила сборку, содержащую данный тип в другом домене приложения.   Возможно, среда выполнения не сможет загрузить сборку, если другой домен приложения настроен отлично от исходного домена приложения.   Например, у двух доменов приложения могут быть различные значения для свойства <xref:System.AppDomain.BaseDirectory%2A>.  
  
-   Запрошенная сборка повреждена или не является сборкой.  
  
-   Код, который пытается загрузить сборку, не имеет соответствующих разрешений на управление доступом для кода для загрузки сборок.  
  
-   Учетная запись пользователя не предоставляет требуемых разрешений, необходимых для чтения файла.  
  
## Решение  
 Первое, что необходимо сделать, — определить, почему среда CLR не может связаться с запрошенной сборкой.   Существует множество причин, почему среде выполнения не удалось найти или загрузить запрошенную сборку, например, сценарии, перечисленные в разделе "Причины".  Чтобы устранить причину ошибки привязки, рекомендуется выполнить следующие действия:  
  
-   Определение причины с помощью данных, предоставленных MDA `bindingFailure`:  
  
    -   Запустить [Fuslogvw.exe \(Assembly Binding Log Viewer\)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md), чтобы прочесть журналы ошибок, созданные связывателем сборок.  
  
    -   Определить, находится ли сборка в запрошенном расположении.   При использовании методов <xref:System.Reflection.Assembly.LoadFrom%2A> и <xref:System.Reflection.Assembly.LoadFile%2A> можно легко определить запрошенное расположение.  При использовании метода <xref:System.Reflection.Assembly.Load%2A>, который осуществляет привязку с помощью удостоверения сборки, следует сначала найти сборки, которые соответствуют данному удостоверению, в пути поиска свойства <xref:System.AppDomain.BaseDirectory%2A> домена приложения и в глобальном кэше сборок.  
  
-   Устранение ошибки в зависимости от результатов предшествующего определения.   Возможны следующие варианты решения:  
  
    -   Установите требуемую сборку в глобальный кэш сборок и вызовите метод  <xref:System.Reflection.Assembly.Load%2A>, чтобы загрузить сборку по ее идентификации.  
  
    -   Скопировать запрошенную сборку в каталог приложения и вызвать метод <xref:System.Reflection.Assembly.Load%2A>, чтобы загрузить сборку по удостоверению.  
  
    -   Выполнить повторную настройку домена приложения, в котором произошла ошибка привязки, чтобы включить путь сборки посредством изменения свойства <xref:System.AppDomain.BaseDirectory%2A> или добавления закрытых путей поиска.  
  
    -   Изменить список управления доступом для файла, чтобы разрешить подключенному пользователю чтение файла.  
  
## Влияние на среду выполнения  
 Данный помощник по отладке управляемого кода не оказывает влияния на среду CLR.  Он только сообщает сведения об ошибках привязки.  
  
## Output  
 MDA сообщает сведения о сборке, которую не удалось загрузить, включая запрошенный путь и\/или отображаемое имя, контекст привязки, домен приложения, в котором была запрошена сборка, и причину возникновения ошибки.  
  
 Отображаемое имя или запрошенный путь могут быть пустыми, если данные недоступны для среды CLR.  Если неудачный вызов был адресован методу <xref:System.Reflection.Assembly.Load%2A>, вероятнее всего, среде выполнения не удалось определить отображаемое имя сборки.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <bindingFailure />  
  </assistants>  
</mdaConfig>  
```  
  
## Пример  
 В следующем примере кода демонстрируется ситуация, в которой может активироваться данный помощник по отладке управляемого кода:  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Reflection;  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // This call attempts to load a nonexistent assembly.  
            // The call will throw a System.IO.FileNotFound exception  
            // and cause the activation of the bindingFailure MDA   
            // if it is registered.  
            Assembly.Load("NonExistentAssembly");  
        }  
    }  
}  
```  
  
## См. также  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)