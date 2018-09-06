---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c77d063d64354bf4693ce82509f36be9d2e5b0c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44035961"
---
# <a name="-doc"></a>-doc
Обрабатывает комментарии к документации в XML-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a>Аргументы  
  
|Термин|Определение|  
|---|---|  
|`+` &#124; `-`|Необязательный. Указание +, или просто `-doc`, компилятор создает документацию и поместите его в XML-файл. Указание `-` эквивалентно отсутствию `-doc`, вызывая нет сведений о документации.|  
|`file`|Является обязательным, если используется параметр `-doc:`. Указывает выходной XML-файл, который заполняется комментариями из файлов исходного кода, компиляции. Если имя файла содержит пробел, заключите его в кавычки (» «).|  
  
## <a name="remarks"></a>Примечания  
 `-doc` Определяет, допустимо ли компилятор создает XML-файл, содержащий комментарии к документации. Если вы используете `-doc:file` синтаксис, `file` параметр указывает имя XML-файла. Если вы используете `-doc` или `-doc+`, компилятор принимает имя XML-файла из исполняемого файла или библиотеки, создаваемой компилятором. Если вы используете `-doc-` или не указывайте `-doc` параметр, компилятор не создает XML-файл.  
  
 В файлах исходного кода комментарии документации могут предшествовать следующие определения:  
  
-   Определяемые пользователем типы, такие как [класс](../../../visual-basic/language-reference/statements/class-statement.md) или [интерфейса](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Члены, например поле, [событий](../../../visual-basic/language-reference/statements/event-statement.md), [свойство](../../../visual-basic/language-reference/statements/property-statement.md), [функция](../../../visual-basic/language-reference/statements/function-statement.md), или [подпрограммы](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Чтобы использовать созданный XML-файл с помощью Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) компонентов, имя XML-файла совпадать с именем сборки, которую требуется поддерживать. Убедитесь, что XML-файл находится в том же каталоге, что и сборка, таким образом, чтобы при ссылке на сборку в проект Visual Studio, XML-файл находится также. Файлы XML-документации не являются обязательными для работы для кода в проекте или в рамках проектов ссылается проект IntelliSense.  
  
 Если при компиляции `/target:module`, XML-файл содержит теги `<assembly></assembly>`. Эти теги укажите имя файла, содержащего манифест сборки для выходного файла компиляции.  
  
 См. в разделе [теги для комментариев XML](../../../visual-basic/language-reference/xmldoc/index.md) способы создания документации из комментариев в коде.  
  
|Чтобы задать - doc в Visual Studio интегрированной среды разработки|  
|---|  
|1.  Выберите проект в **Обозревателе решений**. В меню **Проект** выберите пункт **Свойства**. <br />2.  Откройте вкладку **Компиляция**.<br />3.  Задайте значение в **создать XML-файл документации** поле.|  
  
## <a name="example"></a>Пример  
 См. в разделе [документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) образец.  
  
## <a name="see-also"></a>См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
