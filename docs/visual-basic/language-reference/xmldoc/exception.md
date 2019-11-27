---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e1e7f2d0fb06599f83ba224ed52a10429d9b11fe
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346963"
---
# <a name="exception-visual-basic"></a>> \<исключений (Visual Basic)
Указывает, какие исключения могут быть созданы.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a>Параметры  
 `member`  
 Ссылка на исключение, которое доступно из текущей среды компиляции. Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных. `member` необходимо заключать в двойные кавычки (" ").  
  
 `description`  
 Описание.  
  
## <a name="remarks"></a>Заметки  
 Используйте тег `<exception>`, чтобы указать, какие исключения могут быть созданы. Этот тег применяется к определению метода.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется тег `<exception>` для описания исключения, которое может вызывать функция `IntDivide`.  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
