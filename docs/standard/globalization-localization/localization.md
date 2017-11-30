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
# <a name="localization"></a>Локализация
Локализация — это процесс перевода ресурсов приложения в локализованные версии для каждого языка и региональных параметров, который поддерживает приложение. Переход к этапу локализации должен происходить только после завершения [локализуемости](../../../docs/standard/globalization-localization/localizability-review.md) чтобы удостовериться, что международное приложение готово к локализации.  
  
 Приложение, готовое к локализации разделено на два блока, блок, содержащий все элементы пользовательского интерфейса и блок, содержащий исполняемый код. Блок пользовательского интерфейса содержит только локализуемые интерфейсе элементы, такие как строки, сообщения об ошибках, диалоговые окна, меню, внедренные объектные ресурсы и так далее для нейтрального языка и региональных параметров. Блок кода содержит только код приложения, который будет использоваться для всех поддерживаемых языков и региональных параметров. Общеязыковая среда выполнения поддерживает модели ресурсов вспомогательной сборки, которая отделяет исполняемый код приложения от его ресурсов. Дополнительные сведения о реализации этой модели см. в разделе [ресурсы в классических приложениях](../../../docs/framework/resources/index.md).  
  
 Для каждой локализованной версии приложения добавьте новый вспомогательную сборке, которая содержит блок локализованный пользовательский интерфейс, преобразуется в соответствующий язык для целевого языка и региональных параметров. Блок кода для всех языков и региональных параметров должен оставаться одинаковым. Объединение локализованной версии блок пользовательского интерфейса с помощью блока кода создает локализованную версию приложения.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Предоставляет редактор ресурсов Windows Forms (Winres.exe), позволяющий быстро локализации форм Windows Forms для целевых языков и региональных параметров. Сведения об использовании этого инструмента см. в разделе [Winres.exe (редактор ресурсов Windows Forms)](../../../docs/framework/tools/winres-exe-windows-forms-resource-editor.md).  
  
## <a name="see-also"></a>См. также  
 [Глобализация и локализация](../../../docs/standard/globalization-localization/index.md)  
 [Анализ локализуемости](../../../docs/standard/globalization-localization/localizability-review.md)  
 [Глобализация](../../../docs/standard/globalization-localization/globalization.md)  
 [Ресурсы в приложениях для настольных систем](../../../docs/framework/resources/index.md)
