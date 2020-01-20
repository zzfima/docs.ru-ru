---
title: -baseaddress (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: f138f445b8a335c7505e25b34f560c4da40ab2dd
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937213"
---
# <a name="-baseaddress-c-compiler-options"></a><span data-ttu-id="e2b68-102">-baseaddress (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="e2b68-102">-baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="e2b68-103">Параметр **-baseaddress** позволяет указать предпочтительный базовый адрес для загрузки библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="e2b68-103">The **-baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="e2b68-104">Дополнительные сведения о случаях использования этого параметра см. в [блоге Ларри Остермана (Larry Osterman)](https://docs.microsoft.com/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span><span class="sxs-lookup"><span data-stu-id="e2b68-104">For more information about when and why to use this option, see [Larry Osterman's WebLog](https://docs.microsoft.com/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b68-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2b68-105">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2b68-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e2b68-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="e2b68-107">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="e2b68-107">The base address for the DLL.</span></span> <span data-ttu-id="e2b68-108">Этот адрес можно задать в десятичном, шестнадцатеричном или восьмеричном формате.</span><span class="sxs-lookup"><span data-stu-id="e2b68-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2b68-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2b68-109">Remarks</span></span>  
 <span data-ttu-id="e2b68-110">Базовый адрес по умолчанию для библиотеки DLL задается в среде CLR платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e2b68-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="e2b68-111">Обратите внимание, что младшее слово этого адреса будет округляться.</span><span class="sxs-lookup"><span data-stu-id="e2b68-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="e2b68-112">Например, значение 0x11110001 округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="e2b68-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="e2b68-113">Чтобы завершить процесс подписи для библиотеки DLL, используйте файл SN. EXE с параметром -R.</span><span class="sxs-lookup"><span data-stu-id="e2b68-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e2b68-114">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e2b68-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="e2b68-115">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="e2b68-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="e2b68-116">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="e2b68-116">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="e2b68-117">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="e2b68-117">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="e2b68-118">Измените свойство **Базовый адрес DLL**.</span><span class="sxs-lookup"><span data-stu-id="e2b68-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="e2b68-119">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="e2b68-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2b68-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e2b68-120">See also</span></span>

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e2b68-121">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="e2b68-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e2b68-122">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="e2b68-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
