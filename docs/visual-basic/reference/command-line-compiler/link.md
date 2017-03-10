---
title: "/link (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/l - параметр компилятора [Visual Basic]"
  - "/link - параметр компилятора [Visual Basic]"
  - "внедрение типов взаимодействия [COM-взаимодействие]"
  - "EmbedInteropTypes"
  - "l - параметр компилятора [Visual Basic]"
  - "-l - параметр компилятора [Visual Basic]"
  - "link - параметр компилятора [Visual Basic]"
  - "-link - параметр компилятора [Visual Basic]"
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# /link (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает компилятору сделать доступными для текущего компилируемого проекта сведения о типах COM, находящихся в указанных сборках.  
  
## Синтаксис  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`fileList`|Обязательный.  Список имен файлов сборки с элементами отделенными между собой запятыми.  Заключите имя файла в кавычки \(""\), если оно содержит пробел.|  
  
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
  
 Для указания каталога, в котором находится одна или несколько сборок, на которые идут ссылки, используется параметр [\/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md).  
  
 Подобно параметру компилятора [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md) параметр компилятора `/link` использует файл ответов Vbc.rsp, который ссылается на часто используемые сборки [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  Параметр компилятора [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) позволяет запретить компилятору использовать файл Vbc.rsp.  
  
 Сокращенная форма `/link` — `/l`.  
  
## Универсальные и внедренные типы  
 В последующих разделах описываются ограничения на использование универсальных типов в приложениях с внедренными типами взаимодействия.  
  
### Универсальные интерфейсы  
 Универсальные интерфейсы, внедренные из сборки взаимодействия, использовать невозможно.  Это показано в следующем примере.  
  
 [!code-vb[VbLinkCompiler#1](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/vblinkcompiler/module1.vb#1)]  
  
### Типы с универсальными параметрами  
 Типы с универсальным параметром, тип которого внедрен из сборки взаимодействия, использовать невозможно, если это тип из внешней сборки.  Это ограничение не распространяется на интерфейсы.  Например, рассмотрим интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, определенный в сборке <xref:Microsoft.Office.Interop.Excel>.  Если библиотека содержит внедренные типы из <xref:Microsoft.Office.Interop.Excel> и предоставляет метод, возвращающий универсальный тип с параметром, тип которого — интерфейс <xref:Microsoft.Office.Interop.Excel.Range>, то этот метод должен возвращать универсальный интерфейс, как показано в следующем примере кода.  
  
 [!code-vb[VbLinkCompiler#2](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/vblinkcompiler/utility.vb#2)]  
[!code-vb[VbLinkCompiler#3](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/vblinkcompiler/utility.vb#3)]  
[!code-vb[VbLinkCompiler#4](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/vblinkcompiler/utility.vb#4)]  
  
 В следующем примере клиентский код может вызывать метод, возвращающий универсальный интерфейс <xref:System.Collections.IList>, без ошибок.  
  
 [!code-vb[VbLinkCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/vblinkcompiler/module1.vb#5)]  
  
## Пример  
 Следующий код компилирует исходный файл `OfficeApp.vb`, а также ссылается на сборки из `COMData1.dll` и `COMData2.dll` для создания программы `OfficeApp.exe`.  
  
```vb#  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [\/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Знакомство с COM\-взаимодействием](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)