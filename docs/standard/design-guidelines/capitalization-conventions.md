---
title: Соглашения о написании прописными буквами
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ef7913a2601c3a791cb028b4074ce37b9e9421b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575288"
---
# <a name="capitalization-conventions"></a>Соглашения о написании прописными буквами
Правила, описанные в этой главе размещать простой способ проверки с помощью варианта, при применении единообразно идентификаторы делать для типов, членов и параметров, удобном для чтения.  
  
## <a name="capitalization-rules-for-identifiers"></a>Правила использования прописных букв для идентификаторов  
 Чтобы различать слова в идентификаторе, преобразование первой буквы каждого слова в идентификаторе. Не используйте символы подчеркивания для разделения слов, или по этой причине в любом месте идентификаторы. Существует два способа соответствующие прописной идентификаторов, в зависимости от использования идентификатора:  
  
-   PascalCasing  
  
-   camelCasing  
  
 Соглашение о PascalCasing, используется для всех идентификаторов, за исключением имен параметров, первая буква каждого слова (включая акронимов через из двух букв), как показано в следующих примерах:  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 Особым случаем совершается двухбуквенных акронимах, в которых заданы оба букв, как показано в следующий идентификатор:  
  
 `IOStream`  
  
 Соглашение о camelCasing, используется только для имен параметров, первая буква каждого слова, кроме первого, как показано в следующих примерах. Как показано в примере, двухбуквенных акронимах, начинающиеся стиля Camel присутствуют нижний регистр.  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 **✓ DO** использовать PascalCasing для всех открытых элемента, типа и пространство имен имен, состоящих из нескольких слов.  
  
 **✓ DO** использовать camelCasing для имен параметров.  
  
 Следующая таблица описывает правила использования прописных букв для различных типов идентификаторов.  
  
|Идентификатор|Регистр|Пример|  
|----------------|------------|-------------|  
|Пространство имен|Pascal|`namespace System.Security { ... }`|  
|Тип|Pascal|`public class StreamReader { ... }`|  
|Интерфейс|Pascal|`public interface IEnumerable { ... }`|  
|Метод|Pascal|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|Свойство.|Pascal|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|событие|Pascal|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|Поле|Pascal|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|Значение перечисления|Pascal|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|Параметр|Стиль Camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a>Прописной буквы в составных словах и общих терминов  
 Большинство составные термины рассматриваются как отдельные слова в целях использования прописных букв.  
  
 **X DO NOT** прописных так называемые единым составные слова.  
  
 Это сложные слова, которые написаны как одно слово, например конечной точки. С целью правила определения регистра обрабатывать составное слово единым как одно слово. Используете текущий словарь для определения, если составное слово записывается в закрытой формой.  
  
|Pascal|Стиль Camel|не|  
|------------|-----------|---------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## <a name="case-sensitivity"></a>Учет регистра  
 Языки, которые могут выполняться в среде CLR не требуются для поддержки чувствительность к регистру, несмотря на то, что некоторые выполнять. Даже если его поддерживает ваш язык, другими языками, может получить доступ к вашей платформы нет. Интерфейсы API, доступны извне, таким образом, нельзя полагаться на случай отдельно, чтобы различать два имени, в том же контексте.  
  
 **X DO NOT** предполагается, что все языки программирования чувствительны к регистру. Это не так. Имена не могут различаться только регистром.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)
