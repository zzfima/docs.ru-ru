---
title: "Решение проблемы: кадры PNG в объектах Icon"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2115f2cec327603373ebf566b4d6ccef6404c895
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-png-frames-in-icon-objects"></a><span data-ttu-id="e04b7-102">Решение проблемы: кадры PNG в объектах Icon</span><span class="sxs-lookup"><span data-stu-id="e04b7-102">Mitigation: PNG Frames in Icon Objects</span></span>
<span data-ttu-id="e04b7-103">начиная с версии .NET Framework 4.6 метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> успешно преобразует значки с кадрами PNG в объекты <xref:System.Drawing.Bitmap> .</span><span class="sxs-lookup"><span data-stu-id="e04b7-103">Starting with the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> method successfully converts icons with PNG frames into <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="e04b7-104">В приложениях, предназначенных для .NET Framework 4.5.2 и более ранних версий, метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> создает исключение <xref:System.ArgumentOutOfRangeException> , если объект <xref:System.Drawing.Icon> содержит кадры PNG.</span><span class="sxs-lookup"><span data-stu-id="e04b7-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> method throws an <xref:System.ArgumentOutOfRangeException> exception if the <xref:System.Drawing.Icon> object has PNG frames.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e04b7-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="e04b7-105">Impact</span></span>  
 <span data-ttu-id="e04b7-106">Это изменение затрагивает приложения, которые компилируются повторно для платформы .NET Framework 4.6 и в которых реализуется специальная обработка исключения <xref:System.ArgumentOutOfRangeException> , создаваемого при наличии кадров PNG в объекте <xref:System.Drawing.Icon> .</span><span class="sxs-lookup"><span data-stu-id="e04b7-106">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an <xref:System.Drawing.Icon> object has PNG frames.</span></span> <span data-ttu-id="e04b7-107">При выполнении в .NET Framework 4.6 преобразование проходит успешно, исключение <xref:System.ArgumentOutOfRangeException> больше не создается, и поэтому обработчик исключений больше не вызывается.</span><span class="sxs-lookup"><span data-stu-id="e04b7-107">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>  
  
### <a name="mitigation"></a><span data-ttu-id="e04b7-108">Уменьшение</span><span class="sxs-lookup"><span data-stu-id="e04b7-108">Mitigation</span></span>  
 <span data-ttu-id="e04b7-109">Если такое поведение нежелательно, можно сохранить прежнее поведение, добавив в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="e04b7-109">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 <span data-ttu-id="e04b7-110">Если файл app.config уже содержит элемент `AppContextSwitchOverrides`, новое значение следует объединить с атрибутом `value` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e04b7-110">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the `value` attribute like this:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="e04b7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e04b7-111">See Also</span></span>  
 [<span data-ttu-id="e04b7-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="e04b7-112">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

