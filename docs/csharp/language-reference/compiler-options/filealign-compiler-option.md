---
title: "-filealign (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /filealign
dev_langs:
- CSharp
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1b13dee0a221bc0b97349be5897a04188304ff16
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="filealign-c-compiler-options"></a><span data-ttu-id="f6137-102">/filealign (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f6137-102">/filealign (C# Compiler Options)</span></span>
<span data-ttu-id="f6137-103">Параметр **/filealign** позволяет указать размер разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="f6137-103">The **/filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6137-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6137-104">Syntax</span></span>  
  
```console  
/filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="f6137-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f6137-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="f6137-106">Значение, которое задает размер разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="f6137-106">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="f6137-107">Допустимые значения: 512, 1024, 2048, 4096 и 8192.</span><span class="sxs-lookup"><span data-stu-id="f6137-107">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="f6137-108">Эти значения указаны в байтах.</span><span class="sxs-lookup"><span data-stu-id="f6137-108">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6137-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6137-109">Remarks</span></span>  
 <span data-ttu-id="f6137-110">Каждый раздел выравнивается по границе, кратной значению **/filealign**.</span><span class="sxs-lookup"><span data-stu-id="f6137-110">Each section will be aligned on a boundary that is a multiple of the **/filealign** value.</span></span> <span data-ttu-id="f6137-111">Фиксированный размер по умолчанию не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="f6137-111">There is no fixed default.</span></span> <span data-ttu-id="f6137-112">Если значение **/filealign** не указано, среда CLR выбирает значение по умолчанию во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="f6137-112">If **/filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="f6137-113">Указанный размер раздела влияет на размер выходного файла.</span><span class="sxs-lookup"><span data-stu-id="f6137-113">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="f6137-114">Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.</span><span class="sxs-lookup"><span data-stu-id="f6137-114">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="f6137-115">Используйте [DUMPBIN](/cpp/build/reference/dumpbin-options) для просмотра информации о разделах выходного файла.</span><span class="sxs-lookup"><span data-stu-id="f6137-115">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f6137-116">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f6137-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="f6137-117">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="f6137-117">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="f6137-118">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="f6137-118">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="f6137-119">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="f6137-119">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="f6137-120">Измените свойство **Выравнивание файла**.</span><span class="sxs-lookup"><span data-stu-id="f6137-120">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="f6137-121">Сведения об установке этого параметра компилятора программными средствами см. в статье <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="f6137-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6137-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f6137-122">See Also</span></span>  
 <span data-ttu-id="f6137-123">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6137-123">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="f6137-124">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="f6137-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

