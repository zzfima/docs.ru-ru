---
title: Исключение комментария XML должно иметь атрибут cref
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 54965f3796b6c5ef0e387cd354abcb5740476257
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321178"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a><span data-ttu-id="afeba-102">Исключение комментария XML должно иметь атрибут cref</span><span class="sxs-lookup"><span data-stu-id="afeba-102">XML comment exception must have a 'cref' attribute</span></span>

<span data-ttu-id="afeba-103">Тег \<exception > предоставляет способ документирования исключений, которые могут быть созданы методом.</span><span class="sxs-lookup"><span data-stu-id="afeba-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="afeba-104">Обязательный атрибут `cref` обозначает имя члена, который проверяется генератором документации.</span><span class="sxs-lookup"><span data-stu-id="afeba-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="afeba-105">Если элемент существует, он преобразуется в каноническое имя элемента в файле документации.</span><span class="sxs-lookup"><span data-stu-id="afeba-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>

<span data-ttu-id="afeba-106">**Идентификатор ошибки:** BC42319</span><span class="sxs-lookup"><span data-stu-id="afeba-106">**Error ID:** BC42319</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="afeba-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="afeba-107">To correct this error</span></span>

<span data-ttu-id="afeba-108">Добавьте в исключение атрибут `cref` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="afeba-108">Add the `cref` attribute to the exception as follows:</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="see-also"></a><span data-ttu-id="afeba-109">См. также</span><span class="sxs-lookup"><span data-stu-id="afeba-109">See also</span></span>

- [<span data-ttu-id="afeba-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="afeba-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [<span data-ttu-id="afeba-111">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="afeba-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [<span data-ttu-id="afeba-112">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="afeba-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
