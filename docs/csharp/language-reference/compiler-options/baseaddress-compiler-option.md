---
title: "-baseaddress (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dllbase
dev_langs:
- CSharp
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 18
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
ms.openlocfilehash: 91193ae794957b5045a225614d6322e86d18d459
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="baseaddress-c-compiler-options"></a><span data-ttu-id="f3eb9-102">/baseaddress (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f3eb9-102">/baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="f3eb9-103">Параметр **/baseaddress** позволяет указать предпочтительный базовый адрес для загрузки библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-103">The **/baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="f3eb9-104">Дополнительные сведения о случаях использования этого параметра см. в разделе [Ускорение запуска приложений](http://go.microsoft.com/fwlink/?LinkId=107043) и в [блоге Ларри Остермана (Larry Osterman)](http://go.microsoft.com/fwlink/?LinkId=107044).</span><span class="sxs-lookup"><span data-stu-id="f3eb9-104">For more information about when and why to use this option, see [Improving Application Startup Time](http://go.microsoft.com/fwlink/?LinkId=107043) and [Larry Osterman's WebLog](http://go.microsoft.com/fwlink/?LinkId=107044).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3eb9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3eb9-105">Syntax</span></span>  
  
```console  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="f3eb9-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f3eb9-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="f3eb9-107">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-107">The base address for the DLL.</span></span> <span data-ttu-id="f3eb9-108">Этот адрес можно задать в десятичном, шестнадцатеричном или восьмеричном формате.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3eb9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3eb9-109">Remarks</span></span>  
 <span data-ttu-id="f3eb9-110">Базовый адрес по умолчанию для библиотеки DLL задается в среде CLR платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="f3eb9-111">Обратите внимание, что младшее слово этого адреса будет округляться.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="f3eb9-112">Например, значение 0x11110001 округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="f3eb9-113">Чтобы завершить процесс подписи для библиотеки DLL, используйте файл SN. EXE с параметром -R.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="f3eb9-114">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3eb9-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="f3eb9-115">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-115">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="f3eb9-116">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="f3eb9-117">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="f3eb9-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="f3eb9-118">Измените свойство **Базовый адрес DLL**.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="f3eb9-119">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3eb9-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3eb9-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f3eb9-120">See Also</span></span>  
 <span data-ttu-id="f3eb9-121"><xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f3eb9-121"><xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="f3eb9-122">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="f3eb9-122">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="f3eb9-123">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="f3eb9-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

