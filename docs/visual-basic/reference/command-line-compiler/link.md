---
title: "/ LINK (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e98c855f0a0185e9d1b6682df9fc734e9f1f07bc
ms.lasthandoff: 03/13/2017

---
# <a name="link-visual-basic"></a>/link (Visual Basic)
Указывает компилятору сделать доступными для проекта, компилируемого в текущий момент сведения о типах COM в указанных сборках.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`fileList`|Обязательный. Разделенный запятыми список имен файлов сборки. Если имя файла содержит пробел, заключите имя в кавычки.|  
  
## <a name="remarks"></a>Примечания  
 `/link` Позволяет развернуть приложение, содержащее внедренные сведения о типе. Затем приложение может использовать типы в сборке среды выполнения, реализующие внедренные сведения о типах, не ссылаясь на сборку среды выполнения. Если опубликовано несколько версий сборки среды выполнения, приложение, содержащее внедренные сведения о типах может работать с различными версиями без перекомпиляции. Например, в разделе [Пошаговое руководство: внедрение типов из управляемых сборок](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).  
  
 С помощью `/link` параметр особенно полезен при работе с COM-взаимодействия. Типы COM можно внедрять, чтобы приложение больше не требуется основной сборки взаимодействия (PIA) на конечном компьютере. `/link` Предписывает компилятору внедрить сведения о типах COM из указанной сборки взаимодействия в полученный скомпилированный код. Тип модели COM определяется значение CLSID (идентификатор GUID). В результате приложение может выполняться на конечном компьютере, на который установлен те же типы COM с теми же значениями CLSID. Приложения, автоматизирующие Microsoft Office — хороший пример. Так приложений, таких как Office обычно одно и то же значение CLSID в различных версиях, приложение может использовать ссылочных типов COM, как долго, как .NET Framework 4 или более поздней версии установлен на целевом компьютере и приложение использует методы, свойства или события, включенные в ссылочные типы COM.  
  
 `/link` Позволяет внедрять только интерфейсы, структуры и делегаты. Внедрение COM-классов не поддерживается.  
  
> [!NOTE]
>  При создании экземпляра внедренного типа COM в коде, необходимо создать экземпляр, используя соответствующий интерфейс. Попытка создать экземпляр внедренного типа COM с помощью компонентного класса приводит к ошибке.  
  
 Чтобы задать `/link` параметр в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], добавьте ссылку на сборку и задайте `Embed Interop Types` свойства **true**. Значение по умолчанию для `Embed Interop Types` свойство **false**.  
  
 Если ссылка на сборку COM (сборку A) который сам ссылается на другую сборку COM (сборку Б), необходимо также ссылку на сборку Б, если выполняется любое из следующих действий:  
  
-   Из сборки A тип наследуется от типа или реализует интерфейс из сборки б.  
  
-   Вызывается поле, свойство, событие или метод, который имеет возвращаемый тип или параметр типа из сборки Б.  
  
 Используйте [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) указать каталог, в котором находится один или несколько ссылки на сборки.  
  
 Как [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) параметр компилятора `/link` использует файл ответов Vbc.rsp, который ссылается на часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки. Используйте [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) параметр компилятора, если не хотите, чтобы компилятор использовал файл Vbc.rsp.  
  
 Краткая форма `/link` — `/l`.  
  
## <a name="generics-and-embedded-types"></a>Универсальные и внедренные типы  
 В следующих разделах описаны ограничения на использование универсальных типов в приложениях, внедрение типов взаимодействия.  
  
### <a name="generic-interfaces"></a>Универсальные интерфейсы  
 Нельзя использовать универсальные интерфейсы, внедренные из сборки взаимодействия. Эти действия показаны в следующем примере.  
  
 [!code-vb[VbLinkCompiler&#1;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]  
  
### <a name="types-that-have-generic-parameters"></a>Типы с универсальными параметрами  
 Типы, которые имеют общий параметр, тип которого внедрен из сборки взаимодействия не может использоваться при, тип из внешней сборки. Это ограничение не применяется к интерфейсам. Например, рассмотрим <xref:Microsoft.Office.Interop.Excel.Range>интерфейс, который определен в <xref:Microsoft.Office.Interop.Excel>сборки.</xref:Microsoft.Office.Interop.Excel> </xref:Microsoft.Office.Interop.Excel.Range> Если библиотека содержит внедренные типы взаимодействия из <xref:Microsoft.Office.Interop.Excel>и предоставляет метод, возвращающий универсальный тип, который имеет параметр, тип которого является <xref:Microsoft.Office.Interop.Excel.Range>интерфейс, что метод должен возвращать универсальный интерфейс, как показано в следующем примере кода.</xref:Microsoft.Office.Interop.Excel.Range> </xref:Microsoft.Office.Interop.Excel>  
  
 [!code-vb[VbLinkCompiler&#2;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]  
[!code-vb[VbLinkCompiler&#3;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]  
[!code-vb[VbLinkCompiler&#4;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]  
  
 В следующем примере клиентский код может вызывать метод, возвращающий <xref:System.Collections.IList>универсальный интерфейс без ошибок.</xref:System.Collections.IList>  
  
 [!code-vb[VbLinkCompiler&#5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]  
  
## <a name="example"></a>Пример  
 Следующий код компилирует исходный файл `OfficeApp.vb` и ссылки на сборки из `COMData1.dll` и `COMData2.dll` для создания `OfficeApp.exe`.  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Пошаговое руководство: Внедрение типов из управляемых сборок](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [/ LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md)   
 [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Знакомство с COM-взаимодействием](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
