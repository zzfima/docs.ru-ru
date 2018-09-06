---
title: Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 7dbb15c43d044e21c9823c4a1652b0408006e5c3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032771"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)
`My.Resources` Объект предоставляет доступ к ресурсам приложения и позволяет динамически получать ресурсы для приложения.  
  
## <a name="retrieving-resources"></a>Извлечение ресурсов  
 Множество ресурсов, таких как звуковые файлы, значки, изображения и строки можно извлечь с помощью `My.Resources` объекта. Например можно получить доступ к файлы ресурсов, связанные с языком и региональными параметрами приложения. В следующем примере задается значок формы на значок с именем `Form1Icon` хранятся в файле ресурсов приложения.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 `My.Resources` Объект предоставляет только глобальные ресурсы. Она предоставляет доступ к файлам ресурсов, связанных с формами. Доступ к ресурсам формы необходимо из формы.  
  
 Аналогичным образом `My.Settings` объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения для вашего приложения. Дополнительные сведения см. в разделе [объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md) и [объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>См. также  
 [Объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [Объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [Доступ к параметрам приложения](../../../visual-basic/developing-apps/programming/app-settings/index.md)
