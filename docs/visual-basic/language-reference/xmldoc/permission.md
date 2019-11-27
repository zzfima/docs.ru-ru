---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 71b00b669804e644d1171480192b9d55455bdf53
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352268"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="7b642-101">> разрешений \<(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b642-101">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="7b642-102">Указывает требуемое разрешение для элемента.</span><span class="sxs-lookup"><span data-stu-id="7b642-102">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b642-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b642-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b642-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b642-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="7b642-105">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="7b642-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="7b642-106">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="7b642-106">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="7b642-107">Заключите `member` в кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="7b642-107">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="7b642-108">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="7b642-108">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b642-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="7b642-109">Remarks</span></span>  
 <span data-ttu-id="7b642-110">Используйте тег `<permission>` для документирования доступа к элементу.</span><span class="sxs-lookup"><span data-stu-id="7b642-110">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="7b642-111">Используйте класс <xref:System.Security.PermissionSet>, чтобы указать доступ к элементу.</span><span class="sxs-lookup"><span data-stu-id="7b642-111">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="7b642-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="7b642-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b642-113">Пример</span><span class="sxs-lookup"><span data-stu-id="7b642-113">Example</span></span>  
 <span data-ttu-id="7b642-114">В этом примере используется тег `<permission>`, описывающий, что <xref:System.Security.Permissions.FileIOPermission> требуется для метода `ReadFile`.</span><span class="sxs-lookup"><span data-stu-id="7b642-114">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="7b642-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7b642-115">See also</span></span>

- [<span data-ttu-id="7b642-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="7b642-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
