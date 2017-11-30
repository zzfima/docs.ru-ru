---
title: /doc
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2490529b951ef6e583e3bfa54afced89c823e874
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="doc"></a>/doc
Обрабатывает комментарии к документации в XML-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательно. Указание +, или просто `/doc`, компилятор создает документацию и поместите его в XML-файл. Указание `-` эквивалентно отсутствию `/doc`, вызывая нет сведений о документации.|  
|`file`|Является обязательным, если используется параметр `/doc:`. Задает выходной файл XML, который заполняется комментарии из файлов исходного кода для компиляции. Если имя файла содержит пробелы, следует заключить имя в кавычки (» «).|  
  
## <a name="remarks"></a>Примечания  
 `/doc` Параметр элементы управления ли компилятор создает XML-файл, содержащий комментарии документации. Если вы используете `/doc:``file` синтаксис, `file` задает имя XML-файла. Если вы используете `/doc` или `/doc+`, компилятор принимает имя XML-файла из исполняемого файла или библиотеки, создаваемой компилятором. Если вы используете `/doc-` или не указывайте `/doc` , компилятор не создает XML-файл.  
  
 В файлах исходного кода комментариям документации могут предшествовать следующие определения:  
  
-   Определяемые пользователем типы, такие как [класса](../../../visual-basic/language-reference/statements/class-statement.md) или [интерфейса](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Члены, например поле, [событий](../../../visual-basic/language-reference/statements/event-statement.md), [свойство](../../../visual-basic/language-reference/statements/property-statement.md), [функция](../../../visual-basic/language-reference/statements/function-statement.md), или [подпрограммы](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Чтобы использовать созданный XML-файл с [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) компонента, имя XML-файла совпадать с именем сборки, которую требуется поддерживать. Убедитесь, что XML-файл в том же каталоге, что и сборка, если ссылка на сборку в [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] проекта, XML-файл был найден. XML-файлы документации не требуются для работы для кода в проекте или в проектах, на которые имеются ссылки в проект IntelliSense.  
  
 Если при компиляции `/target:module`, XML-файл содержит теги `<assembly></assembly>`. Эти теги указывают имя файла, содержащего манифест сборки для выходного файла компиляции.  
  
 В разделе [теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) способы создания документации из комментариев в коде.  
  
|Задание/doc в Visual Studio интегрированной среде разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Откройте вкладку **Компиляция**.<br />3.  Задайте значение в **создать XML-файл документации** поле.|  
  
## <a name="example"></a>Пример  
 В разделе [документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) образец.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
