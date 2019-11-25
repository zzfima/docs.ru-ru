---
title: Применимость функциональных преобразований
ms.date: 07/20/2015
ms.assetid: 3b74e134-e19b-44bc-8d06-e26c48305040
ms.openlocfilehash: 292201f4964142126d428939807cb20f354a7d2f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345773"
---
# <a name="applicability-of-functional-transformation-visual-basic"></a>Applicability of Functional Transformation (Visual Basic)
Чисто функциональные преобразования применяются в самых разнообразных ситуациях.  
  
 Подход с использованием функциональных преобразований идеально подходит для запросов и управления структурированными данными, поэтому вполне соответствует технологиям LINQ. Но функциональные преобразования могут применяться гораздо шире, чем только в LINQ. Любой процесс, основной задачей которого является преобразование данных из одной формы в другую, может считаться применимым для функционального преобразования.  
  
 Этот подход можно использовать при решении многих задач, даже если на первый взгляд кажется, что он неприменим. Применение функциональных преобразований в сочетании с технологиями LINQ или без них должно рассматриваться при работе со следующими объектами.  
  
- Документы на основе XML. Имеющие правильный формат данные на любом диалекте языка XML могут быть легко подвергнуты функциональным преобразованиям. For more information, see [Functional Transformation of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md).  
  
- Другие структурированные форматы файлов. Большинство файлов, от Windows.ini до обычных текстовых документов, имеют определенную структуру, которую можно анализировать и преобразовывать.  
  
- Протоколы потоковых данных. Кодирование и декодирование данных в коммуникационных протоколах часто можно представить в виде простого функционального преобразования.  
  
- Данные RDBMS и OODBMS. Реляционные и объектно-ориентированные базы данных, как и XML, являются широко используемыми структурированными источниками данных.  
  
- Математические, статистические и научные решения. В этих областях происходит обработка больших наборов данных, чтобы пользователь мог представлять визуально, оценивать или действительно решить нетривиальные задачи.  
  
 As described in [Refactoring Into Pure Functions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md), using pure functions is an example of functional programming. Кроме очевидных преимуществ чистых функций, их применение позволяет получить ценный опыт решения проблем с точки зрения применения функциональных преобразований. Такой подход может серьезно повлиять на стиль программирования и конструирования классов. Это особенно важно, если задача легко решается путем преобразования данных, как описано выше.  
  
 Безусловно, это не относится к теме данного учебника, но следует отметить, что проекты, разработанные с учетом возможностей функциональных преобразований, чаще всего бывают сосредоточены на применении в качестве действующих факторов процессов, а не объектов, а полученное в результате решение чаще всего бывает реализовано как ряд крупномасштабных преобразований, а не как изменения состояний отдельных объектов.  
  
 Again, remember that Visual Basic supports both imperative and functional approaches, so the best design for your application might incorporate elements of both.  
  
## <a name="see-also"></a>См. также

- [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Функциональное преобразование XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-transformation-of-xml.md)
- [Refactoring Into Pure Functions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/refactoring-into-pure-functions.md)
