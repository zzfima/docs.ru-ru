---
title: Быстрая разработка приложений с использованием My.Resources и My.Settings
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: ce9a5bf76ba3132f58aa40227a145d8b5bf1591d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349266"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)

Объект `My.Resources` предоставляет доступ к ресурсам приложения и позволяет динамически получать ресурсы для приложения.  
  
## <a name="retrieving-resources"></a>Извлечение ресурсов  

 С помощью объекта `My.Resources` можно получить ряд ресурсов, таких как звуковые файлы, значки, изображения и строки. Например, можно получить доступ к файлам ресурсов, относящимся к языку и региональным параметрам приложения. В следующем примере значок формы задается значком с именем `Form1Icon`, хранящимся в файле ресурсов приложения.  
  
 [!code-vb[VbVbcnMy#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#7)]  
  
 Объект `My.Resources` предоставляет только глобальные ресурсы. Он не предоставляет доступ к файлам ресурсов, связанным с формами. Необходимо получить доступ к ресурсам формы из формы.  
  
 Аналогичным образом объект `My.Settings` предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать параметры свойств и другие сведения для приложения. Дополнительные сведения см. в разделе [My. Resources](../../../visual-basic/language-reference/objects/my-resources-object.md) Object и [My. Settings](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>См. также

- [Объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md)
- [Объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Доступ к параметрам приложения](../../../visual-basic/developing-apps/programming/app-settings/index.md)
