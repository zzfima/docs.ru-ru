---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 904d573514bf35b773d47321b7fd3b6a86e90262
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524699"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="94e78-102">> \<permission (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94e78-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="94e78-103">Указывает требуемое разрешение для элемента.</span><span class="sxs-lookup"><span data-stu-id="94e78-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94e78-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="94e78-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94e78-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="94e78-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="94e78-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="94e78-107">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="94e78-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="94e78-108">Заключите `member` в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="94e78-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="94e78-109">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="94e78-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94e78-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="94e78-110">Remarks</span></span>  
 <span data-ttu-id="94e78-111">Используйте тег `<permission>` для документирования доступа к элементу.</span><span class="sxs-lookup"><span data-stu-id="94e78-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="94e78-112">Используйте класс <xref:System.Security.PermissionSet>, чтобы указать доступ к элементу.</span><span class="sxs-lookup"><span data-stu-id="94e78-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="94e78-113">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="94e78-113">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e78-114">Пример</span><span class="sxs-lookup"><span data-stu-id="94e78-114">Example</span></span>  
 <span data-ttu-id="94e78-115">В этом примере используется тег `<permission>`, описывающий, что <xref:System.Security.Permissions.FileIOPermission> требуется для метода `ReadFile`.</span><span class="sxs-lookup"><span data-stu-id="94e78-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="94e78-116">См. также</span><span class="sxs-lookup"><span data-stu-id="94e78-116">See also</span></span>

- [<span data-ttu-id="94e78-117">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="94e78-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
