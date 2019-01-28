---
title: Руководство по программированию на C#. &lt;include&gt;
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- include
- <include>
helpviewer_keywords:
- <include> C# XML tag
- include C# XML tag
ms.assetid: a8a70302-6196-4643-bd09-ef33f411f18f
ms.openlocfilehash: a9e87e803bef38ceb91849b976e2019deed54471
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541174"
---
# <a name="ltincludegt-c-programming-guide"></a>&lt;include&gt; (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<include file='filename' path='tagpath[@name="id"]' />  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Имя XML-файла, содержащего документацию. Имя файла может быть квалифицировано с помощью относительного пути к файлу исходного кода. `filename` необходимо заключать в одинарные кавычки (' ').  
  
 `tagpath`  
 Путь тегов в `filename`, который ведет к тегу `name`. Путь необходимо заключать в одинарные кавычки (' ').  
  
 `name`  
 Спецификатор имени в теге, предшествующий комментариям. `name` будет иметь идентификатор `id`.  
  
 `id`  
 Идентификатор тега, который предшествует комментариям. Идентификатор заключается в двойные кавычки (" ").  
  
## <a name="remarks"></a>Примечания  
 Тег \<include> позволяет задать ссылку на комментарии в другом файле, которые описывают типы и члены вашего исходного кода. Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода. Помещая комментарии документации в отдельный файл, вы можете реализовать управление их версиями отдельно от версий исходного кода. В этом случае файл исходного кода может быть извлечен для изменения одним пользователем, а файл документации — другим.  
  
 Тег \<include> использует XML-синтаксис XPath. Сведения об использовании тега \<include> см. в документации по XPath.  
  
## <a name="example"></a>Пример  
 В этом примере представлено несколько файлов. Ниже показан первый файл, в котором используется тег \<include>:  
  
 [!code-csharp[csProgGuideDocComments#5](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/include_1.cs)]  
  
 Второй файл (xml_include_tag.doc) содержит следующие комментарии документации:  
  
```xml  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## <a name="program-output"></a>Выходные данные программы  
 При компиляции классов Test и Test2 с использованием следующей команды в командной строке создаются следующие выходные данные: `/doc:DocFileName.xml.` В Visual Studio параметр "Комментарии XML-документа" задается в области построения конструктора проектов. При обнаружении тега \<include> компилятор C# ведет поиск комментариев документации в файле xml_include_tag.doc вместо текущего файла исходного кода. После этого компилятор создает файл DocFileName.xml, который будет использоваться средствами для работы с документацией, такими как [Sandcastle](https://github.com/EWSoftware/SHFB), для подготовки окончательной версии документации.  
  
```xml  
<?xml version="1.0"?>   
<doc>   
    <assembly>   
        <name>xml_include_tag</name>   
    </assembly>   
    <members>   
        <member name="T:Test">   
            <summary>   
The summary for this type.   
</summary>   
        </member>   
        <member name="T:Test2">   
            <summary>   
The summary for this other type.   
</summary>   
        </member>   
    </members>   
</doc>   
```  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
