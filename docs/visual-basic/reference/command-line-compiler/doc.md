---
title: "/ doc | Документы Microsoft"
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
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 1054eb256eb7670ee0454b02fc094e0306c1218d
ms.lasthandoff: 03/13/2017

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
|`+` &#124; `-`|Необязательный. Указание +, или просто `/doc`, указывает компилятору сгенерировать сведения о документации и поместить его в XML-файл. Указание `-` является эквивалентом неуказанного `/doc`, вызывая нет сведений о документации.|  
|`file`|Является обязательным, если используется параметр `/doc:`. Задает выходной файл XML, который заполняется комментариями из файлов исходного кода компиляции. Если имя файла содержит пробел, заключите имя в кавычки (» «).|  
  
## <a name="remarks"></a>Примечания  
 `/doc` Параметр определяет, будет ли компилятор создает XML-файл, содержащий комментарии к документации. Если вы используете `/doc:``file` синтаксис, `file` задает имя XML-файла. Если вы используете `/doc` или `/doc+`, компилятор принимает имя XML-файла из исполняемого файла или библиотеки, который создается компилятором. Если вы используете `/doc-` или не указывать `/doc` , компилятор не создает XML-файл.  
  
 В файлах исходного кода комментариям документации могут предшествовать следующие определения:  
  
-   Определяемые пользователем типы, такие как [класса](../../../visual-basic/language-reference/statements/class-statement.md) или [интерфейс](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Члены, например поле, [событий](../../../visual-basic/language-reference/statements/event-statement.md), [свойство](../../../visual-basic/language-reference/statements/property-statement.md), [функция](../../../visual-basic/language-reference/statements/function-statement.md), или [подпрограммы](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Чтобы использовать созданный XML-файл с [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] [IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) компонента, имя XML-файла совпадать с именем сборки, которую требуется поддерживать. Убедитесь, что XML-файл в том же каталоге, что и сборка, если ссылка на сборку в [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] проекта, XML-файл был найден. XML-файлы документации не требуются для работы в проекте или в проектах ссылается проект кода IntelliSense.  
  
 Если при компиляции `/target:module`, XML-файл содержит теги `<assembly></assembly>`. Эти теги укажите имя файла, содержащего манифест сборки для выходного файла компиляции.  
  
 В разделе [теги XML-комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) способы создания документации из комментариев в коде.  
  
|Установка/doc в Visual Studio интегрированная среда разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. На **проекта** меню, щелкните **свойства**. Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Откройте вкладку **Компиляция**.<br />3.  Задайте значение в **создать XML-файл документации** поле.|  
  
## <a name="example"></a>Пример  
 В разделе [документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) образец.  
  
## <a name="see-also"></a>См. также  
 [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
