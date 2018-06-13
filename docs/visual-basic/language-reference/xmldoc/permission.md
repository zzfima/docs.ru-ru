---
title: '&lt;разрешение&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 4fafebf94be350951672f01f2d17bd00d4bab69a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601999"
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="486f7-102">&lt;разрешение&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="486f7-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="486f7-103">Указывает разрешение, необходимые для элемента.</span><span class="sxs-lookup"><span data-stu-id="486f7-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="486f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="486f7-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="486f7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="486f7-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="486f7-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="486f7-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="486f7-107">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="486f7-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="486f7-108">Заключите `member` в кавычки (» «).</span><span class="sxs-lookup"><span data-stu-id="486f7-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="486f7-109">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="486f7-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="486f7-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="486f7-110">Remarks</span></span>  
 <span data-ttu-id="486f7-111">Используйте `<permission>` тег для документирования доступ к члену.</span><span class="sxs-lookup"><span data-stu-id="486f7-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="486f7-112">Используйте <xref:System.Security.PermissionSet> классу, чтобы задать доступ к члену.</span><span class="sxs-lookup"><span data-stu-id="486f7-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="486f7-113">Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="486f7-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="486f7-114">Пример</span><span class="sxs-lookup"><span data-stu-id="486f7-114">Example</span></span>  
 <span data-ttu-id="486f7-115">В этом примере используется `<permission>` тегов для описания, <xref:System.Security.Permissions.FileIOPermission> затребована `ReadFile` метод.</span><span class="sxs-lookup"><span data-stu-id="486f7-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="486f7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="486f7-116">See Also</span></span>  
 [<span data-ttu-id="486f7-117">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="486f7-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
