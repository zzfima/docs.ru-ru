---
title: '&#39;&lt;Имя интерфейса&gt;.&lt; имя пользователя&gt; &#39; уже реализован базовым классом &#39; &lt;имя_базового_класса&gt;&#39;. Повторная реализация &lt;тип&gt; предполагается, что'
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 9054c293ede9db4637f23579407f2f76db29f2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588974"
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a>&#39;&lt;Имя интерфейса&gt;.&lt; имя пользователя&gt; &#39; уже реализован базовым классом &#39; &lt;имя_базового_класса&gt;&#39;. Повторная реализация &lt;тип&gt; предполагается, что
Свойство, процедура или событие в производном классе использует `Implements` предложение указания элемента интерфейса, который уже реализован в базовом классе.  
  
 Производный класс может повторно реализовать элемент интерфейса, который реализован его базовым классом. Это не та же переопределяющая реализация базового класса. Дополнительные сведения см. в разделе [реализует](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42015  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если вы собираетесь реализовать элемент интерфейса, вам не нужно предпринимать никаких действий. Код в производном классе получает доступ к повторно реализованному элементу, если вы используете `MyBase` ключевое слово для доступа к реализации базового класса.  
  
-   Если вы не собираетесь реализовать элемент интерфейса, удалите предложение `Implements` из свойства, процедуры или объявления события.  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
