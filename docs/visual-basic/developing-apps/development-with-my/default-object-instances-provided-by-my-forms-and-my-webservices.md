---
title: Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 9285e88e3dc9fd8b3731416b1c40811188d6a33d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563604"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)
[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) и [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) объекты предоставляют доступ к формам, источникам данных и веб-служб XML, используемой приложением. Это делается путем предоставления коллекций *по умолчанию экземпляры* каждого из этих объектов.  
  
## <a name="default-instances"></a>Экземпляры по умолчанию  
 Экземпляр по умолчанию является экземпляром класса, который предоставляется средой выполнения и не нужно быть объявляется и создается с помощью `Dim` и `New` инструкций. В следующем примере показано, как вы может объявляется и создается экземпляр <xref:System.Windows.Forms.Form> класс с именем `Form1`, и как вы, теперь могут получить экземпляр по умолчанию это <xref:System.Windows.Forms.Form> класса через `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 `My.Forms` Объект возвращает коллекцию экземпляров по умолчанию для каждого `Form` класс, который существует в проекте. Аналогичным образом `My.WebServices` предоставляет экземпляр по умолчанию прокси-класса для каждой веб-службы, что вы создали ссылку в приложении.  
  
## <a name="see-also"></a>См. также
- [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
