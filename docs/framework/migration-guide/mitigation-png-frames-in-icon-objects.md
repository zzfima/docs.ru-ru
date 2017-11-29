---
title: "Решение проблемы: кадры PNG в объектах Icon"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dbc81484f55cabbdc86e7ba57e68f9e1c96a567f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-png-frames-in-icon-objects"></a><span data-ttu-id="428b5-102">Решение проблемы: кадры PNG в объектах Icon</span><span class="sxs-lookup"><span data-stu-id="428b5-102">Mitigation: PNG Frames in Icon Objects</span></span>
<span data-ttu-id="428b5-103">начиная с версии .NET Framework 4.6 метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> успешно преобразует значки с кадрами PNG в объекты <xref:System.Drawing.Bitmap> .</span><span class="sxs-lookup"><span data-stu-id="428b5-103">Starting with the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="428b5-104">В приложениях, предназначенных для .NET Framework 4.5.2 и более ранних версий, метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> создает исключение <xref:System.ArgumentOutOfRangeException> , если объект <xref:System.Drawing.Icon> содержит кадры PNG.</span><span class="sxs-lookup"><span data-stu-id="428b5-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the <xref:System.Drawing.Icon> object has PNG frames.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="428b5-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="428b5-105">Impact</span></span>  
 <span data-ttu-id="428b5-106">Это изменение затрагивает приложения, которые компилируются повторно для платформы .NET Framework 4.6 и в которых реализуется специальная обработка исключения <xref:System.ArgumentOutOfRangeException> , создаваемого при наличии кадров PNG в объекте <xref:System.Drawing.Icon> .</span><span class="sxs-lookup"><span data-stu-id="428b5-106">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an <xref:System.Drawing.Icon> object has PNG frames.</span></span> <span data-ttu-id="428b5-107">При выполнении в .NET Framework 4.6 преобразование проходит успешно, исключение <xref:System.ArgumentOutOfRangeException> больше не создается, и поэтому обработчик исключений больше не вызывается.</span><span class="sxs-lookup"><span data-stu-id="428b5-107">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>  
  
### <a name="mitigation"></a><span data-ttu-id="428b5-108">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="428b5-108">Mitigation</span></span>  
 <span data-ttu-id="428b5-109">Если такое поведение нежелательно, можно сохранить прежнее поведение, добавив в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="428b5-109">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 <span data-ttu-id="428b5-110">Если файл app.config уже содержит элемент `AppContextSwitchOverrides`, новое значение следует объединить с атрибутом `value` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="428b5-110">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the `value` attribute like this:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="428b5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="428b5-111">See Also</span></span>  
 [<span data-ttu-id="428b5-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="428b5-112">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
