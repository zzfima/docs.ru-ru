---
title: "Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7339afdc35341739b592b2a327094754031c346c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)
`My.Resources` Объект предоставляет доступ к ресурсам приложения и позволяет динамически извлекать ресурсы для приложения.  
  
## <a name="retrieving-resources"></a>Извлечение ресурсов  
 Ряд ресурсов, таких как звуковые файлы, значки, изображения и строки можно извлечь с помощью `My.Resources` объекта. Например можно получить доступ к файлы ресурсов для определенных языка и региональных параметров приложения. В следующем примере задается значок формы на значок с именем `Form1Icon` хранятся в файле ресурсов приложения.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 `My.Resources` Объект предоставляет только глобальные ресурсы. Он не предоставляет доступ к файлам ресурсов, связанных с формами. Для доступа к ресурсам формы из формы.  
  
 Аналогичным образом `My.Settings` объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения о приложении. Дополнительные сведения см. в разделе [My.Resources-объект](../../../visual-basic/language-reference/objects/my-resources-object.md) и [My.Settings-объект](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>См. также  
 [Объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [Объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [Доступ к параметрам приложения](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
