---
title: "-baseaddress (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7cd3269754f783ab8b26683f5215aa81825673e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="baseaddress-c-compiler-options"></a><span data-ttu-id="c3371-102">/baseaddress (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="c3371-102">/baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="c3371-103">Параметр **/baseaddress** позволяет указать предпочтительный базовый адрес для загрузки библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="c3371-103">The **/baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="c3371-104">Дополнительные сведения о когда и почему следует использовать этот параметр, см. в разделе [блога Ларри Osterman](http://go.microsoft.com/fwlink/?LinkId=107044).</span><span class="sxs-lookup"><span data-stu-id="c3371-104">For more information about when and why to use this option, see [Larry Osterman's WebLog](http://go.microsoft.com/fwlink/?LinkId=107044).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3371-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3371-105">Syntax</span></span>  
  
```console  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="c3371-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c3371-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="c3371-107">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="c3371-107">The base address for the DLL.</span></span> <span data-ttu-id="c3371-108">Этот адрес можно задать в десятичном, шестнадцатеричном или восьмеричном формате.</span><span class="sxs-lookup"><span data-stu-id="c3371-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3371-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3371-109">Remarks</span></span>  
 <span data-ttu-id="c3371-110">Базовый адрес по умолчанию для библиотеки DLL задается в среде CLR платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c3371-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="c3371-111">Обратите внимание, что младшее слово этого адреса будет округляться.</span><span class="sxs-lookup"><span data-stu-id="c3371-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="c3371-112">Например, значение 0x11110001 округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="c3371-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="c3371-113">Чтобы завершить процесс подписи для библиотеки DLL, используйте файл SN. EXE с параметром -R.</span><span class="sxs-lookup"><span data-stu-id="c3371-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c3371-114">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c3371-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="c3371-115">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="c3371-115">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="c3371-116">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="c3371-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="c3371-117">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="c3371-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="c3371-118">Измените свойство **Базовый адрес DLL**.</span><span class="sxs-lookup"><span data-stu-id="c3371-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="c3371-119">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="c3371-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3371-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c3371-120">See Also</span></span>  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c3371-121">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="c3371-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="c3371-122">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="c3371-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
