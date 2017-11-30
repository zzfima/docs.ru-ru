---
title: "Безопасность поставщиков типов"
description: "Дополнительные сведения о безопасность поставщиков типов F #, включая изменение параметров доверия для поставщика типов."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9c5a8a1f-5a31-490d-83c0-8beabda75c78
ms.openlocfilehash: c8f03ee90d4dce1d3484a9dfe8951d500d509a2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="type-provider-security"></a><span data-ttu-id="43533-104">Безопасность поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="43533-104">Type Provider Security</span></span>

<span data-ttu-id="43533-105">Поставщики типов являются сборки (DLL) ссылается проекта F # или сценария, содержащие код для подключения к внешним источникам данных и выявить подобные сведения о типах в среде типов F #.</span><span class="sxs-lookup"><span data-stu-id="43533-105">Type providers are assemblies (DLLs) referenced by your F# project or script that contain code to connect to external data sources and surface this type information to the F# type environment.</span></span> <span data-ttu-id="43533-106">Как правило код в указанных сборках, выполняется только при компиляции и затем выполните код (или в случае сценария, отправить код в F # Interactive).</span><span class="sxs-lookup"><span data-stu-id="43533-106">Typically, code in referenced assemblies is only run when you compile and then execute the code (or in the case of a script, send the code to F# Interactive).</span></span> <span data-ttu-id="43533-107">Тем не менее сборки поставщика типа выполняется в среде Visual Studio, если код просто просмотреть в редакторе.</span><span class="sxs-lookup"><span data-stu-id="43533-107">However, a type provider assembly will run inside Visual Studio when the code is merely browsed in the editor.</span></span> <span data-ttu-id="43533-108">Это происходит, поскольку тип поставщики должны выполнить, чтобы добавить дополнительные сведения в редактор, например отображение кратких сведений, завершения IntelliSense и т. д.</span><span class="sxs-lookup"><span data-stu-id="43533-108">This happens because type providers need to run to add extra information to the editor, such as Quick Info tooltips, IntelliSense completions, and so on.</span></span> <span data-ttu-id="43533-109">В результате могут возникать дополнительные проблемы безопасности для типа сборки поставщика, так как они автоматически выполняться внутри процесса Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="43533-109">As a result, there are extra security considerations for type provider assemblies, since they run automatically inside the Visual Studio process.</span></span>


## <a name="security-warning-dialog"></a><span data-ttu-id="43533-110">Диалоговое окно предупреждения системы безопасности</span><span class="sxs-lookup"><span data-stu-id="43533-110">Security Warning Dialog</span></span>
<span data-ttu-id="43533-111">При использовании сборки поставщика определенного типа в первый раз, Visual Studio отображает диалоговое окно, предупреждающее о том, что поставщик типов сейчас будет запущена.</span><span class="sxs-lookup"><span data-stu-id="43533-111">When using a particular type provider assembly for the first time, Visual Studio displays a security dialog that warns you that the type provider is about to run.</span></span> <span data-ttu-id="43533-112">До Visual Studio загружает поставщика типов, дает возможность решить, если вы доверяете этого конкретного поставщика.</span><span class="sxs-lookup"><span data-stu-id="43533-112">Before Visual Studio loads the type provider, it gives you the opportunity to decide if you trust this particular provider.</span></span> <span data-ttu-id="43533-113">Если вы доверяете источнику поставщика типов, затем выберите «Доверять ли поставщик типов».</span><span class="sxs-lookup"><span data-stu-id="43533-113">If you trust the source of the type provider, then select "I trust this type provider."</span></span> <span data-ttu-id="43533-114">Если вы не доверяете источнику типа поставщика, затем выберите «Я не доверяйте этот поставщик типов».</span><span class="sxs-lookup"><span data-stu-id="43533-114">If you do not trust the source of the type provider, then select "I do not trust this type provider."</span></span> <span data-ttu-id="43533-115">Предоставление доверия поставщик позволяет ему выполняются в Visual Studio и обеспечить поддержку технологии IntelliSense и создавать компоненты.</span><span class="sxs-lookup"><span data-stu-id="43533-115">Trusting the provider enables it to run inside Visual Studio and provide IntelliSense and build features.</span></span> <span data-ttu-id="43533-116">Однако если поставщик типа вредоносных, выполнению его кода, может нанести ущерб компьютере.</span><span class="sxs-lookup"><span data-stu-id="43533-116">But if the type provider itself is malicious, running its code could compromise your machine.</span></span>

<span data-ttu-id="43533-117">Если проект содержит код, ссылающийся на поставщиков типов, которые были выбраны в диалоговом окне не отмечен как доверенный, затем во время компиляции, компилятор выдает ошибку, указывающую, что поставщик типа не является доверенным.</span><span class="sxs-lookup"><span data-stu-id="43533-117">If your project contains code that references type providers that you chose in the dialog not to trust, then at compile time, the compiler will report an error that indicates that the type provider is untrusted.</span></span> <span data-ttu-id="43533-118">Все типы, которые зависят от поставщика ненадежных типа обозначаются красные волнистые линии.</span><span class="sxs-lookup"><span data-stu-id="43533-118">Any types that are dependent on the untrusted type provider are indicated by red squiggles.</span></span> <span data-ttu-id="43533-119">Можно безопасно можно просмотреть в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="43533-119">It is safe to browse the code in the editor.</span></span>

<span data-ttu-id="43533-120">Если вы решите изменить параметр доверия непосредственно в Visual Studio, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="43533-120">If you decide to change the trust setting directly in Visual Studio, perform the following steps.</span></span>


#### <a name="to-change-the-trust-settings-for-type-providers"></a><span data-ttu-id="43533-121">Чтобы изменить параметры доверия для поставщиков типов</span><span class="sxs-lookup"><span data-stu-id="43533-121">To change the trust settings for type providers</span></span>

1. <span data-ttu-id="43533-122">На `Tools` последовательно выберите пункты `Options`и разверните `F# Tools` узла.</span><span class="sxs-lookup"><span data-stu-id="43533-122">On the `Tools` menu, select `Options`, and expand the `F# Tools` node.</span></span>
<br />

2. <span data-ttu-id="43533-123">Выберите `Type Providers`, в списке поставщиков типов, установите флажок для доверенных поставщиков типов и установите флажки для тех, которым не вы доверяете.</span><span class="sxs-lookup"><span data-stu-id="43533-123">Select `Type Providers`, and in the list of type providers, select the check box for type providers you trust, and clear the check box for those you don't trust.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="43533-124">См. также</span><span class="sxs-lookup"><span data-stu-id="43533-124">See Also</span></span>
[<span data-ttu-id="43533-125">Поставщики типов</span><span class="sxs-lookup"><span data-stu-id="43533-125">Type Providers</span></span>](index.md)
