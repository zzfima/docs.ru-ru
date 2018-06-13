---
title: Локализация
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7fc995843c1e2f5977acbfe2158457d30ac355ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573917"
---
# <a name="localization"></a><span data-ttu-id="a4bb6-102">Локализация</span><span class="sxs-lookup"><span data-stu-id="a4bb6-102">Localization</span></span>
<span data-ttu-id="a4bb6-103">Локализацией называется процесс преобразования ресурсов приложения в локализованные версии для конкретных языков и региональных параметров, которые приложение должно поддерживать.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-103">Localization is the process of translating an application's resources into localized versions for each culture that the application will support.</span></span> <span data-ttu-id="a4bb6-104">К этапу локализации следует приступать только после [проверки локализуемости](../../../docs/standard/globalization-localization/localizability-review.md), которая позволяет проверить готовность глобализованного приложения к локализации.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-104">You should proceed to the localization step only after completing the [Localizability Review](../../../docs/standard/globalization-localization/localizability-review.md) step to verify that the globalized application is ready for localization.</span></span>  
  
 <span data-ttu-id="a4bb6-105">Готовое к локализации приложение разделяется на два логических блока. Один из них содержит все элементы пользовательского интерфейса, а другой — исполняемый код.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-105">An application that is ready for localization is separated into two conceptual blocks, a block that contains all user interface elements and a block that contains executable code.</span></span> <span data-ttu-id="a4bb6-106">Блок пользовательского интерфейса содержит только локализуемые элементы, например строки, сообщения об ошибках, диалоговые окна, пункты меню, внедренные объектные ресурсы и т. д. для нейтрального языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-106">The user interface block contains only localizable user-interface elements such as strings, error messages, dialog boxes, menus, embedded object resources, and so on for the neutral culture.</span></span> <span data-ttu-id="a4bb6-107">Блок кода содержит только код приложения, который будет одинаковым для всех поддерживаемых языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-107">The code block contains only the application code to be used by all supported cultures.</span></span> <span data-ttu-id="a4bb6-108">Общеязыковая среда выполнения поддерживает модель ресурсов вспомогательной сборки, в которой исполняемый код приложения отделен от его ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-108">The common language runtime supports a satellite assembly resource model that separates an application's executable code from its resources.</span></span> <span data-ttu-id="a4bb6-109">Более подробную информацию о реализации этой модели см. в статье [Ресурсы в приложениях для настольных систем](../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="a4bb6-109">For more information about implementing this model, see [Resources in Desktop Apps](../../../docs/framework/resources/index.md).</span></span>  
  
 <span data-ttu-id="a4bb6-110">Для каждой локализованной версии приложения добавьте новую вспомогательную сборку, которая содержит локализованный блок пользовательского интерфейса, учитывающий все требования целевого языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-110">For each localized version of your application, add a new satellite assembly that contains the localized user interface block translated into the appropriate language for the target culture.</span></span> <span data-ttu-id="a4bb6-111">Блок кода должен оставаться одинаковым для всех языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-111">The code block for all cultures should remain the same.</span></span> <span data-ttu-id="a4bb6-112">Объединение локализованной версии блока пользовательского интерфейса с блоком кода создает новую локализованную версию приложения.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-112">The combination of a localized version of the user interface block with the code block produces a localized version of your application.</span></span>  
  
 <span data-ttu-id="a4bb6-113">В пакете [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] предоставляется редактор ресурсов Windows Forms (Winres.exe), позволяющий быстро локализовать ресурсы Windows Forms для целевых языков и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a4bb6-113">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] supplies the Windows Forms Resource Editor (Winres.exe) that allows you to quickly localize Windows Forms for target cultures.</span></span> <span data-ttu-id="a4bb6-114">Сведения об использовании этого инструмента см. в статье [Winres.exe (редактор ресурсов Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a4bb6-114">For information about using this tool, see [Winres.exe (Windows Forms Resource Editor)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4bb6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a4bb6-115">See Also</span></span>  
 [<span data-ttu-id="a4bb6-116">Глобализация и локализация</span><span class="sxs-lookup"><span data-stu-id="a4bb6-116">Globalization and Localization</span></span>](../../../docs/standard/globalization-localization/index.md)  
 [<span data-ttu-id="a4bb6-117">Анализ локализуемости</span><span class="sxs-lookup"><span data-stu-id="a4bb6-117">Localizability Review</span></span>](../../../docs/standard/globalization-localization/localizability-review.md)  
 [<span data-ttu-id="a4bb6-118">Глобализация</span><span class="sxs-lookup"><span data-stu-id="a4bb6-118">Globalization</span></span>](../../../docs/standard/globalization-localization/globalization.md)  
 [<span data-ttu-id="a4bb6-119">Ресурсы в приложениях для настольных систем</span><span class="sxs-lookup"><span data-stu-id="a4bb6-119">Resources in Desktop Apps</span></span>](../../../docs/framework/resources/index.md)
