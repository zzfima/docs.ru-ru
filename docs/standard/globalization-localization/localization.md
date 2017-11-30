---
title: "Локализация"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture, localization
- application development [.NET Framework], localization
- globalization [.NET Framework], localization
- code blocks
- international applications [.NET Framework], localization
- global applications, localization
- world-ready applications, localization
- user interface blocks
- localization [.NET Framework], about localization
- localizing resources
ms.assetid: 49d520d7-92d7-44ee-bb24-8b615db1d41b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4aaf2da77a1fab55cbebd6bfa05a2b1c74e5cbbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="localization"></a><span data-ttu-id="796d1-102">Локализация</span><span class="sxs-lookup"><span data-stu-id="796d1-102">Localization</span></span>
<span data-ttu-id="796d1-103">Локализация — это процесс перевода ресурсов приложения в локализованные версии для каждого языка и региональных параметров, который поддерживает приложение.</span><span class="sxs-lookup"><span data-stu-id="796d1-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="796d1-104">Переход к этапу локализации должен происходить только после завершения [локализуемости](../../../docs/standard/globalization-localization/localizability-review.md) чтобы удостовериться, что международное приложение готово к локализации.</span><span class="sxs-lookup"><span data-stu-id="796d1-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>  
  
 <span data-ttu-id="796d1-105">Приложение, готовое к локализации разделено на два блока, блок, содержащий все элементы пользовательского интерфейса и блок, содержащий исполняемый код.</span><span class="sxs-lookup"><span data-stu-id="796d1-105">An application that is ready for localization is separated into two conceptual blocks, a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="796d1-106">Блок пользовательского интерфейса содержит только локализуемые интерфейсе элементы, такие как строки, сообщения об ошибках, диалоговые окна, меню, внедренные объектные ресурсы и так далее для нейтрального языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="796d1-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="796d1-107">Блок кода содержит только код приложения, который будет использоваться для всех поддерживаемых языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="796d1-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="796d1-108">Общеязыковая среда выполнения поддерживает модели ресурсов вспомогательной сборки, которая отделяет исполняемый код приложения от его ресурсов.</span><span class="sxs-lookup"><span data-stu-id="796d1-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="796d1-109">Дополнительные сведения о реализации этой модели см. в разделе [ресурсы в классических приложениях](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="796d1-109">For more information about implementing this model, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="796d1-110">Для каждой локализованной версии приложения добавьте новый вспомогательную сборке, которая содержит блок локализованный пользовательский интерфейс, преобразуется в соответствующий язык для целевого языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="796d1-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="796d1-111">Блок кода для всех языков и региональных параметров должен оставаться одинаковым.</span><span class="sxs-lookup"><span data-stu-id="796d1-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="796d1-112">Объединение локализованной версии блок пользовательского интерфейса с помощью блока кода создает локализованную версию приложения.</span><span class="sxs-lookup"><span data-stu-id="796d1-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>  
  
 <span data-ttu-id="796d1-113">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Предоставляет редактор ресурсов Windows Forms (Winres.exe), позволяющий быстро локализации форм Windows Forms для целевых языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="796d1-113">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="796d1-114">Сведения об использовании этого инструмента см. в разделе [Winres.exe (редактор ресурсов Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="796d1-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="796d1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="796d1-115">See Also</span></span>  
 [<span data-ttu-id="796d1-116">Глобализация и локализация</span><span class="sxs-lookup"><span data-stu-id="796d1-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="796d1-117">Анализ локализуемости</span><span class="sxs-lookup"><span data-stu-id="796d1-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 [<span data-ttu-id="796d1-118">Глобализация</span><span class="sxs-lookup"><span data-stu-id="796d1-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="796d1-119">Ресурсы в приложениях для настольных систем</span><span class="sxs-lookup"><span data-stu-id="796d1-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
