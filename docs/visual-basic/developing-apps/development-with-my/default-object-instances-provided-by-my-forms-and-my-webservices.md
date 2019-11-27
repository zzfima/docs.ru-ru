---
title: Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: d06df4bd023892429b2aaefdd624398a6546d06d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330204"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)

Объекты [My. Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) и [My. WebService](../../../visual-basic/language-reference/objects/my-webservices-object.md) предоставляют доступ к формам, источникам данных и веб-службам XML, используемым приложением. Это делается путем предоставления коллекций *экземпляров по умолчанию* для каждого из этих объектов.  
  
## <a name="default-instances"></a>Экземпляры по умолчанию  

 Экземпляр по умолчанию — это экземпляр класса, который предоставляется средой выполнения и не требует объявления и создания экземпляра с помощью инструкций `Dim` и `New`. В следующем примере показано, как можно было объявить и создать экземпляр <xref:System.Windows.Forms.Form> класса с именем `Form1`, и как теперь можно получить экземпляр по умолчанию этого класса <xref:System.Windows.Forms.Form> через `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 Объект `My.Forms` Возвращает коллекцию экземпляров по умолчанию для каждого класса `Form`, существующего в проекте. Аналогичным образом `My.WebServices` предоставляет экземпляр класса-посредника по умолчанию для каждой веб-службы, на которую вы создали ссылку в приложении.  
  
## <a name="see-also"></a>См. также

- [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [Зависимость My от типа проекта](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
