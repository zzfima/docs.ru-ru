---
title: -filealign (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /filealign
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
ms.openlocfilehash: aed8b412ea1580f7dfa4f87333598d76a85b5e64
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69603012"
---
# <a name="-filealign-c-compiler-options"></a><span data-ttu-id="c7eff-102">-filealign (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="c7eff-102">-filealign (C# Compiler Options)</span></span>
<span data-ttu-id="c7eff-103">Параметр **-filealign** позволяет указать размер разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="c7eff-103">The **-filealign** option lets you specify the size of sections in your output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7eff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7eff-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="c7eff-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c7eff-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="c7eff-106">Значение, которое задает размер разделов в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="c7eff-106">A value that specifies the size of sections in the output file.</span></span> <span data-ttu-id="c7eff-107">Допустимые значения: 512, 1024, 2048, 4096 и 8192.</span><span class="sxs-lookup"><span data-stu-id="c7eff-107">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="c7eff-108">Эти значения указаны в байтах.</span><span class="sxs-lookup"><span data-stu-id="c7eff-108">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7eff-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="c7eff-109">Remarks</span></span>  
 <span data-ttu-id="c7eff-110">Каждый раздел выравнивается по границе, кратной значению **-filealign**.</span><span class="sxs-lookup"><span data-stu-id="c7eff-110">Each section will be aligned on a boundary that is a multiple of the **-filealign** value.</span></span> <span data-ttu-id="c7eff-111">Фиксированный размер по умолчанию не предусмотрен.</span><span class="sxs-lookup"><span data-stu-id="c7eff-111">There is no fixed default.</span></span> <span data-ttu-id="c7eff-112">Если значение **-filealign** не указано, среда CLR выбирает значение по умолчанию во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="c7eff-112">If **-filealign** is not specified, the common language runtime picks a default at compile time.</span></span>  
  
 <span data-ttu-id="c7eff-113">Указанный размер раздела влияет на размер выходного файла.</span><span class="sxs-lookup"><span data-stu-id="c7eff-113">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="c7eff-114">Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.</span><span class="sxs-lookup"><span data-stu-id="c7eff-114">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
 <span data-ttu-id="c7eff-115">Используйте [DUMPBIN](/cpp/build/reference/dumpbin-options) для просмотра информации о разделах выходного файла.</span><span class="sxs-lookup"><span data-stu-id="c7eff-115">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c7eff-116">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7eff-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="c7eff-117">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="c7eff-117">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="c7eff-118">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="c7eff-118">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="c7eff-119">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="c7eff-119">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="c7eff-120">Измените свойство **Выравнивание файла**.</span><span class="sxs-lookup"><span data-stu-id="c7eff-120">Modify the **File Alignment** property.</span></span>  
  
 <span data-ttu-id="c7eff-121">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7eff-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7eff-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c7eff-122">See also</span></span>

- [<span data-ttu-id="c7eff-123">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="c7eff-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c7eff-124">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="c7eff-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
