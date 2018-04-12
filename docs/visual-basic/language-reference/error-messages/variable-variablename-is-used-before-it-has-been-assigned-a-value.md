---
title: Переменная &#39; &lt;variablename&gt;&#39; используется прежде чем ей было присвоено значение
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 201667c250e15bb9af73e64e2d8c924c1952d1be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>Переменная &#39; &lt;variablename&gt;&#39; используется прежде чем ей было присвоено значение
Переменной "\<variablename >" используется, прежде чем ей было присвоено значение. Во время выполнения может возникнуть исключение "пустая ссылка".  
  
 Приложение имеет по крайней мере один возможный путь во всем коде, который считывает значение переменной перед к нему было назначено значение.  
  
 Если переменной никогда не назначалось значение, она содержит значение по умолчанию для своего типа данных. Для ссылочного типа данных, что значение по умолчанию — [ничего не](../../../visual-basic/language-reference/nothing.md). Чтение переменной ссылки, которая имеет значение `Nothing` , в некоторых случаях может привести к исключению <xref:System.NullReferenceException> .  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42104  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте логику потока управления и убедитесь, что переменная имеет допустимое значение, прежде чем управление передается оператору, используемого для чтения.  
  
-   Чтобы гарантировать, что переменная всегда имеет допустимое значение можно инициализировать его в рамках его объявления. В разделе «Инициализация» в [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>См. также  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Устранение неполадок, связанных с переменными](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
