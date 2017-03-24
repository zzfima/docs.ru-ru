---
title: "Устранение неполадок взаимодействия (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interop, deploying assemblies
- assemblies [Visual Basic]
- interop, installing assemblies that share components
- COM objects, troubleshooting
- interop, sharing components
- troubleshooting interoperability
- interoperability, troubleshooting
- COM interop, troubleshooting
- assemblies [Visual Basic], deploying
- troubleshooting Visual Basic, interoperability
- interop assemblies
- interoperability, sharing components
- shared components, using with assemblies
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cbc37638ed5c57b94356c2d189f36b66202ceba5
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-interoperability-visual-basic"></a>Устранение неполадок взаимодействия (Visual Basic)
При взаимодействии между COM и управляемым кодом [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], могут появиться один или несколько из следующих распространенных проблем.  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a>Маршалинг взаимодействия  
 В некоторых случаях может потребоваться использование типов данных, которые не являются частью [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]. Сборки взаимодействия выполняют большую часть работы с объектами COM, но может возникнуть необходимость управления типы данных, которые используются, когда управляемые объекты предоставляются COM. Например, структуры в библиотеках класса необходимо указать `BStr` неуправляемый тип для строк, отправляемых в объекты COM, созданные Visual Basic 6.0 и более ранних версий. В таких случаях можно использовать <xref:System.Runtime.InteropServices.MarshalAsAttribute>атрибут, чтобы управляемые типы предоставлялись как неуправляемые типы.</xref:System.Runtime.InteropServices.MarshalAsAttribute>  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a>Экспорт строк фиксированной длины в неуправляемый код  
 В Visual Basic 6.0 и более ранних версиях строки экспортировались COM-объекты как последовательности байтов без знака с нулем. Для обеспечения совместимости с другими языками [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] при экспорте строк включает завершающий знак. Лучший способ решить проблему несовместимости — экспортировать строки без завершающего знака как массивы `Byte` или `Char`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a>Экспорт иерархий наследования  
 Управляемого класса выравниваются иерархий при представляются в виде COM-объектов. Например если определить базовый класс с элементом и затем наследовать базовый класс в производном классе, который предоставляется как объект COM, клиенты, использующие производный класс в объекте COM будет невозможно использовать унаследованные члены. Члены базового класса из COM-объектов может осуществляться только как экземпляры базового класса, а затем только в том случае, если базовый класс также создан как COM-объект.  
  
## <a name="overloaded-methods"></a>Перегруженные методы  
 Хотя можно создать перегруженные методы с помощью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], они не поддерживаются COM. Когда класс, содержащий перегруженные методы предоставляется как объект COM, новые имена методов создаются для перегруженных методов.  
  
 Например, рассмотрим класс, имеющий две перегрузки `Synch` метод. Когда класс выставлен как объект COM, новые созданные имена методов могут быть `Synch` и `Synch_2`.  
  
 Переименование может вызвать две проблемы для потребителей COM-объекта.  
  
1.  Клиенты могут не ожидать созданных имен методов.  
  
2.  Имена созданных методов в классе, выставленном как COM-объект можно изменить при добавлении новых перегрузок к классу или его базовый класс. Это может вызвать проблемы управления версиями.  
  
 Для решения обоих проблем, присвойте каждому методу уникальное имя вместо использования перегрузки при разработке объектов, которые будут предоставлены в виде COM-объектов.  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a>Использование объектов COM с помощью сборок взаимодействия  
 Сборки взаимодействия используются почти как если бы они были управляемым кодом, заменяющим объекты COM, которые они представляют. Тем не менее поскольку они являются обертками, а не фактические COM-объекты, существуют некоторые различия в использовании сборок взаимодействия и обычных сборок. Эти различия касаются раскрытие классов и типов данных параметров и возвращаемых значений.  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a>Классы, предоставляемые и как интерфейсы и классы  
 В отличие от классов в обычных сборках классы COM представлены в сборках взаимодействия как интерфейс и класс, представляющий COM-класса. Имя интерфейса идентична COM-класса. Имя класса взаимодействия же, что и исходный класс COM, но слово «Class» добавлением. Например предположим, что у вас есть проект со ссылкой на сборку взаимодействия для COM-объекта. Если COM-класс назван `MyComClass`, IntelliSense и обозреватель объектов покажет интерфейс с именем `MyComClass` и класс с именем `MyComClassClass`.  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a>Создание экземпляров класса .NET Framework  
 Как правило, создается экземпляр [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] класса `New` инструкции с именем класса. Наличие класса COM, представленного сборкой взаимодействия — это тот случай, в котором можно использовать `New` инструкции с интерфейсом. Только при использовании COM-класса с `Inherits` инструкции, интерфейс можно использовать так же, как и класс. Следующий код демонстрирует создание `Command` объекта в проекте, который содержит ссылку на библиотеку Microsoft ActiveX данных объектов 2.8 COM-объект:  
  
 [!code-vb[VbVbalrInterop&20;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 Однако при использовании COM-класса как основа для производного класса, необходимо использовать класс взаимодействия, представляющий класс COM, как показано в следующем коде:  
  
 [!code-vb[VbVbalrInterop&#21;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  Сборки взаимодействия неявно реализуют интерфейсы, которые представляют COM-классов. Не следует пытаться использовать `Implements` приведет к инструкции для реализации этих интерфейсов или ошибку.  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a>Типы данных параметров и возвращаемых значений  
 В отличие от элементов обычных сборок члены сборки взаимодействия могут иметь типы данных, которые отличаются от используемых в исходном объявлении объекта. Несмотря на то, что сборки взаимодействия неявно преобразуют типы COM в совместимые типы среды выполнения, следует обратить внимание на типы данных, которые используются с обеих сторон для предотвращения ошибок во время выполнения. Например, в COM-объекты, созданные в Visual Basic 6.0 и более ранних версиях, значения типа `Integer` предполагается [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] эквивалентный тип `Short`. Рекомендуется использовать обозреватель объектов для проверки характеристик импортированных элементов перед их использованием.  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a>Методы COM уровня модуля  
 Большинство объектов COM используются путем создания экземпляра класса COM с помощью `New` ключевое слово и затем вызывает методы этого объекта. Единственным исключением из этого правила включает COM-объекты, содержащие `AppObj` или `GlobalMultiUse` COM-классов. Такие классы напоминают методы уровня модуля в [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] классы. Visual Basic 6.0 и более ранних версиях неявно создает экземпляры таких объектов при первом вызове одного из их методов. Например, в Visual Basic 6.0 можно добавить ссылку на библиотека объектов Microsoft DAO 3.6 и вызов `DBEngine` без предварительного создания экземпляра:  
  
```  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]необходимо всегда создавать экземпляры COM-объектов, перед использованием их методов. Чтобы использовать эти методы в [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], объявите переменную нужного класса и используйте ключевое слово new присвойте объект для переменной объекта. `Shared` Ключевое слово может использоваться при необходимости убедитесь, что только один экземпляр класса создается.  
  
 [!code-vb[VbVbalrInterop&#23;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a>Необработанные ошибки в обработчиках событий  
 Одна из общих проблем взаимодействия касается ошибок в обработчики событий, которые обрабатывают события COM-объектов. Такие ошибки игнорируются, если специально проверки на наличие ошибок с помощью `On Error` или `Try...Catch...Finally` инструкции. Например, следующий пример взят из [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] проект содержит ссылку на библиотеку Microsoft ActiveX данных объектов 2.8 COM-объекта.  
  
 [!code-vb[VbVbalrInterop&#24;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 Этот пример выдает ошибку, как ожидалось. Тем не менее если один и тот же пример без `Try...Catch...Finally` блока, ошибка обрабатывается, как если бы вы использовали `OnError Resume Next` инструкции. Без обработки ошибок деление на ноль вызовет неявную ошибку. Поскольку такие ошибки никогда не вызывают ошибку необработанного исключения, важно использовать определенные виды обработки исключений в обработчики событий, обрабатывающие события из COM-объектов.  
  
### <a name="understanding-com-interop-errors"></a>Основные сведения об ошибках взаимодействия COM  
 Без обработки ошибок вызовы взаимодействия часто создают ошибки, которые предоставляют немного информации. По возможности следует используйте структурированную обработку для предоставления дополнительных сведений о проблемах, при их возникновении ошибок. Это может быть особенно полезно при отладке приложений. Например:  
  
 [!code-vb[VbVbalrInterop&#25;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 Можно найти сведения, такие как описание ошибки, HRESULT и источник ошибок COM. Проверка содержимого объекта исключения.  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a>Проблемы управления ActiveX  
 Большинство элементов управления ActiveX, которые работают с Visual Basic 6.0 работать с [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] без проблем. Большинство исключений — это контейнерные элементы управления или элементы управления, которые визуально содержат другие элементы управления. Некоторые примеры старых элементов управления, которые не работают с [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] выглядят следующим образом:  
  
-   Управление Microsoft Forms 2.0 кадров  
  
-   Управления вверх / вниз, также известный как счетчик  
  
-   Sheridan вкладок  
  
 Существует способов обойти проблемы с неподдерживаемыми элементами управления ActiveX мало. Можно выполнить миграцию существующих элементов управления [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] Если вы являетесь владельцем исходного кода. В противном случае можно проверить с поставщиками программного обеспечения для обновления. NET-совместимой версии элементов управления для замены неподдерживаемые элементы управления ActiveX.  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a>Передача свойства ReadOnly ByRef элементов управления  
 [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]иногда вызывает ошибки COM, такие как «Ошибка 0x800A017F CTL_E_SETNOTSUPPORTED» при передаче `ReadOnly` свойства некоторых старых элементов управления ActiveX, как `ByRef` параметров других процедур. Аналогично, процедура, вызванная в Visual Basic 6.0, не вызывает ошибки, и параметры обрабатываются так, как если бы они передавались по значению. Сообщение об ошибке содержатся в [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] является COM-объектом, сообщение о том, что вы пытаетесь изменить свойство, которое не имеет свойство `Set` процедуры.  
  
 При наличии доступа к вызываемой процедуре можно предотвратить эту ошибку, используя `ByVal` ключевое слово для объявления параметров, принимающих `ReadOnly` свойства. Например:  
  
 [!code-vb[VbVbalrInterop&#26;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 Если нет доступа к исходному коду для вызываемой процедуры, можно принудительно свойство передается по значению, добавив дополнительный набор скобок в вызывающей процедуре. Например в проекте, который содержит ссылку на библиотеку Microsoft ActiveX данных объектов 2.8 COM-объекта, можно использовать:  
  
 [!code-vb[VbVbalrInterop&#27;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a>Развертывание сборок, предоставляющих взаимодействие  
 Развертывание сборок, которые предоставляют интерфейсы COM, связаны особые проблемы. Например потенциальная проблема возникает, когда различные приложения ссылаются на одной и той же сборки COM. Эта ситуация типична при установке новой версии сборки, а старая версия сборки по-прежнему используется другим приложением. При удалении сборки, использующего библиотеку DLL, вы можете оказаться недоступность для других сборок.  
  
 Во избежание этой проблемы следует устанавливать совместно используемые сборки в глобальный кэш сборок (GAC) и использовать MergeModule для этого компонента. Если не удается установить приложение в глобальный кэш СБОРОК, он должен устанавливаться в CommonFilesFolder в подкаталоге конкретных версий.  
  
 Сборки, которые не являются общими должны быть расположены рядом друг с другом в каталоге с вызывающим приложением.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Взаимодействие COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tlbimp.exe (программа импорта библиотек типов)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (программа экспорта библиотек типов)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [Пошаговое руководство: Реализация наследования с использованием COM-объектов](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Глобальный кэш сборок](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202)
