---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 1cbac2162bd39cdc8af9a55dfd6e2f90bc40b08a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354327"
---
# <a name="code-visual-basic"></a>> кода \<(Visual Basic)
Указывает, что текст представляет собой несколько строк кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a>Параметры  
 `content`  
 Текст, помечающий как код.  
  
## <a name="remarks"></a>Заметки  
 Используйте тег `<code>`, чтобы указать несколько строк в виде кода. С помощью тега [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) можно указать, что текст в описании необходимо пометить как код.  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="example"></a>Пример  
 В этом примере используется тег \<Code >, чтобы добавить пример кода для использования поля `ID`.  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [XML-теги для комментариев](../../../visual-basic/language-reference/xmldoc/index.md)
