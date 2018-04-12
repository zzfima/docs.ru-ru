---
title: '&#39; &lt;interfacename&gt;.&lt; имя пользователя&gt;&#39; уже реализован базовым классом &#39;&lt; имя_базового_класса&gt;&#39;. Повторная реализация &lt;тип&gt; предполагается, что'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69884ed567e0046da5cf5c51b3e83e57e890d49f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a>&#39; &lt;interfacename&gt;.&lt; имя пользователя&gt;&#39; уже реализован базовым классом &#39;&lt; имя_базового_класса&gt;&#39;. Повторная реализация &lt;тип&gt; предполагается, что
Свойство, процедура или событие в производном классе использует `Implements` предложение указания элемента интерфейса, который уже реализован в базовом классе.  
  
 Производный класс может повторно реализовать элемент интерфейса, который реализован его базовым классом. Это не та же переопределяющая реализация базового класса. Дополнительные сведения см. в разделе [реализует](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42015  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если вы собираетесь реализовать элемент интерфейса, вам не нужно предпринимать никаких действий. Код в производном классе получает доступ к повторно реализованному элементу, если вы используете `MyBase` ключевое слово для доступа к реализации базового класса.  
  
-   Если вы не собираетесь реализовать элемент интерфейса, удалите предложение `Implements` из свойства, процедуры или объявления события.  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
