---
title: "/link (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/l compiler option [C#]"
  - "/link compiler option [C#]"
  - "-l compiler option [C#]"
  - "EmbedInteropTypes"
  - "l compiler option [C#]"
  - "embed interop types [COM Interop]"
  - "-link compiler option [C#]"
  - "link compiler option [C#]"
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /link (C# Compiler Options)
Указывает компилятору сделать доступными для текущего компилируемого проекта сведения о типах COM, находящихся в указанных сборках.  
  
## Синтаксис  
  
```  
/link:fileList  
// -or-  
/l:fileList  
```  
  
## Аргументы  
 `fileList`  
 Обязательный.  Список имен файлов сборки с элементами отделенными между собой запятыми.  Заключите имя файла в кавычки \(""\), если оно содержит пробел.  
  
## Заметки  
 Параметр `/link` позволяет развернуть приложение, содержащее внедренные сведения о типах.  Такое приложение может использовать типы в сборке среды выполнения, реализующие внедренные сведения о типах, без необходимости ссылаться на сборку среды выполнения.  Если опубликовано несколько версий сборки среды выполнения, приложение, содержащее внедренные сведения о типах, может работать с различными версиями без перекомпиляции.  Пример см. в разделе [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Применение параметра `/link` особенно полезно при работе с COM\-взаимодействием.  Типы COM можно сделать внедренными, и приложение более не будет нуждаться в основной сборке взаимодействия \(primary interop assembly — PIA\) на конечном компьютере.  Параметр `/link` указывает компилятору внедрить сведения о типах COM из указанной сборки взаимодействия в полученный в результате скомпилированный код.  Тип COM определяется по значению CLSID \(GUID\).  В результате приложение может выполняться на конечном компьютере, на котором установлены те же типы COM с теми же значениями CLSID.  Хорошим примером являются приложения, автоматизирующие Microsoft Office.  Поскольку в приложениях, подобных пакету Office, одно и то же значение CLSID обычно сохраняется в различных версиях, приложение пользователя может использовать типы COM по ссылкам при условии, что на конечном компьютере установлена платформа .NET Framework 4 или более поздней версии, а приложение использует методы, свойства или события, включенные в ссылочные типы COM.  
  
 Параметр `/link` позволяет внедрять только интерфейсы, структуры и делегаты.  Внедрение COM\-классов не поддерживается.  
  
> [!NOTE]
>  При создании в коде экземпляра внедренного типа COM необходимо использовать надлежащий интерфейс.  Попытка создать экземпляр внедренного типа COM с помощью компонентного класса приводит к ошибке.  
  
 Чтобы задать значение параметра `/link` в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)], добавьте ссылку на сборку и задайте для свойства `Embed Interop Types` значение **true**.  Для свойства `Embed Interop Types` по умолчанию задано значение **false**.  
  
 Если создается ссылка на сборку COM \(сборку A\), которая сама ссылается на другую сборку COM \(сборку Б\), необходимо также создать ссылку на сборку Б, если любое из следующих утверждений верно.  
  
-   Используемый из сборки A тип наследуется от типа или реализует интерфейс из сборки Б.  
  
-   Вызывается поле, свойство, событие или метод, который возвращает из сборки Б тип или параметр типа.  
  
 Подобно параметру компилятора [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) параметр компилятора `/link` использует файл ответов Csc.rsp, который ссылается на часто используемые сборки [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  Параметр компилятора [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) позволяет запретить компилятору использовать файл Csc.rsp.  
  
 Сокращенная форма `/link` — `/l`.  
  
## Универсальные и внедренные типы  
 В последующих разделах описываются ограничения на использование универсальных типов в приложениях с внедренными типами взаимодействия.  
  
### Универсальные интерфейсы  
 Универсальные интерфейсы, внедренные из сборки взаимодействия, использовать невозможно.  Это показано в следующем примере.  
  
 [!code-cs[VbLinkCompilerCS#1](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/program.cs#1)]  
  
### Типы с универсальными параметрами  
 Типы с универсальным параметром, тип которого внедрен из сборки взаимодействия, использовать невозможно, если это тип из внешней сборки.  Это ограничение не распространяется на интерфейсы.  Например, рассмотрим интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, определенный в сборке <xref:Microsoft.Office.Interop.Excel>.  Если библиотека содержит внедренные типы из <xref:Microsoft.Office.Interop.Excel> и предоставляет метод, возвращающий универсальный тип с параметром, тип которого — интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, то этот метод должен возвращать универсальный интерфейс, как показано в следующем примере кода.  
  
 [!code-cs[VbLinkCompilerCS#2](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/utility.cs#2)]  
[!code-cs[VbLinkCompilerCS#3](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/utility.cs#3)]  
[!code-cs[VbLinkCompilerCS#4](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/utility.cs#4)]  
  
 В следующем примере клиентский код может вызывать метод, возвращающий универсальный интерфейс <xref:System.Collections.IList>, без ошибок.  
  
 [!code-cs[VbLinkCompilerCS#5](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/program.cs#5)]  
  
## Пример  
 Следующий код компилирует исходный файл `OfficeApp.cs` и ссылается на сборки из `COMData1.dll` и `COMData2.dll` для получения `OfficeApp.exe`.  
  
```c#  
csc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)   
 [\/noconfig \(Ignore csc.rsp\)](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [Общие сведения о взаимодействии](../../../csharp/programming-guide/interop/interoperability-overview.md)