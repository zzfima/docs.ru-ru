---
title: Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 421995684201ec48d5e8aff9b0ed7640efd1e4b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)
[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) и [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) объекты предоставляют доступ к формам, источникам данных и веб-служб XML, используемого приложением. Это делается путем предоставления коллекций *экземпляров по умолчанию* каждого из этих объектов.  
  
## <a name="default-instances"></a>Экземпляры по умолчанию  
 Экземпляр по умолчанию является экземпляром класса, который предоставляется средой выполнения и не обязательно должно объявляется и создается с помощью `Dim` и `New` инструкции. В следующем примере показано, как вы может объявляется и создается экземпляр <xref:System.Windows.Forms.Form> класс с именем `Form1`, и как вы теперь можете получить экземпляр по умолчанию это <xref:System.Windows.Forms.Form> класса через `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 `My.Forms` Объект возвращает коллекцию экземпляров по умолчанию для каждого `Form` класс, который существует в проекте. Аналогичным образом `My.WebServices` предоставляет экземпляр по умолчанию прокси-класса для каждой веб-службы, что вы создали ссылку в приложении.  
  
## <a name="see-also"></a>См. также  
 [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
