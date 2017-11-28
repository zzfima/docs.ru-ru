---
title: "-nostdlib (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad3ca7775512623de43c7fe6b7fe1cf481ccca87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="nostdlib-c-compiler-options"></a><span data-ttu-id="69cf9-102">/nostdlib (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="69cf9-102">/nostdlib (C# Compiler Options)</span></span>
<span data-ttu-id="69cf9-103">Параметр**/nostdlib** запрещает импорт библиотеки mscorlib.dll, которая определяет все пространство имен System.</span><span class="sxs-lookup"><span data-stu-id="69cf9-103">**/nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69cf9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69cf9-104">Syntax</span></span>  
  
```console  
/nostdlib[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="69cf9-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="69cf9-105">Remarks</span></span>  
 <span data-ttu-id="69cf9-106">Используйте этот параметр, если вы хотите определить или создать собственное пространство имен System и объекты.</span><span class="sxs-lookup"><span data-stu-id="69cf9-106">Use this option if you want to define or create your own System namespace and objects.</span></span>  
  
 <span data-ttu-id="69cf9-107">Если вы не укажете параметр **/nostdlib**, библиотека mscorlib.dll будет импортирована в вашу программу (как и при указании **/nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="69cf9-107">If you do not specify **/nostdlib**, mscorlib.dll will be imported into your program (same as specifying **/nostdlib-**).</span></span> <span data-ttu-id="69cf9-108">Указание **/nostdlib** дает тот же результат, что и указание **/nostdlib+**.</span><span class="sxs-lookup"><span data-stu-id="69cf9-108">Specifying **/nostdlib** is the same as specifying **/nostdlib+**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="69cf9-109">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="69cf9-109">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="69cf9-110">Откройте страницу **свойств** для проекта.</span><span class="sxs-lookup"><span data-stu-id="69cf9-110">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="69cf9-111">Щелкните страницу свойств **сборки** .</span><span class="sxs-lookup"><span data-stu-id="69cf9-111">Click the **Build** properties page.</span></span>  
  
3.  <span data-ttu-id="69cf9-112">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="69cf9-112">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="69cf9-113">Измените свойство **Не ссылаться на mscorlib.dll** .</span><span class="sxs-lookup"><span data-stu-id="69cf9-113">Modify the **Do not reference mscorlib.dll** property.</span></span>  
  
 <span data-ttu-id="69cf9-114">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="69cf9-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69cf9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="69cf9-115">See Also</span></span>  
 [<span data-ttu-id="69cf9-116">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="69cf9-116">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
