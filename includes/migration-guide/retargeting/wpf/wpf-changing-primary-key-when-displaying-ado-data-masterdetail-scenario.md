---
ms.openlocfilehash: 2cd107dc92fd0fae89717c38840ce7ea44f3ac9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234002"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>Изменение первичного ключа в WPF при отображении данных ADO в сценарии "главный — подчиненный"

|   |   |
|---|---|
|Подробные сведения|Давайте рассмотрим сценарий, в котором у вас есть коллекция ADO с элементами типа <code>Order</code> и отношение с именем &quot;OrderDetails&quot;, которое сопоставляет ее с другой коллекцией элементов типа <code>Detail</code> через первичный ключ &quot;OrderID&quot;. В приложении WPF можно привязать элемент управления "Список" к подробным сведениям о конкретном заказе:<pre><code class="lang-xml">&lt;ListBox ItemsSource=&quot;{Binding Path=OrderDetails}&quot; &gt;&#13;&#10;</code></pre>DataContext имеет значение <code>Order</code>. WPF получает значение свойства <code>OrderDetails</code>, которое представляет собой коллекцию D с элементами <code>Detail</code>, у которых <code>OrderID</code> соответствует <code>OrderID</code> главного элемента. Изменение поведения проявляется, когда вы меняете первичный ключ <code>OrderID</code> для главного элемента. ADO автоматически изменяет <code>OrderID</code> в каждой из затронутых записей в коллекции Details (то есть в тех, которые копируются в коллекцию D).  Что же происходит с коллекцией D?<ul><li>Старое поведение:   коллекция D очищена.   Главный элемент <em>не</em> вызывает уведомление об изменении свойства <code>OrderDetails</code>.  Поле со списком продолжает использовать коллекцию D, которая теперь пуста.</li><li>Новое поведение:  коллекция D — без изменений.   Каждый из ее элементов вызывает уведомление об изменении свойства <code>OrderID</code>.  Поле со списком продолжает использовать коллекцию D и отображает подробные сведения с новым значением <code>OrderID</code>.</li></ul>Чтобы реализовать новое поведение, WPF создает коллекцию D другим способом, вызывая метод ADO <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> с аргументом <code>followParent</code>, который имеет значение <code>true</code>.|
|Предложение|Приложение может получит новое поведение, если указать следующий параметр AppContext.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;&#13;&#10;</code></pre>По умолчанию параметр <code>true</code> (старое поведение) используется для приложений, предназначенных для .NET 4.7.1 или ниже, а <code>false</code> (новое поведение) — для приложений, предназначенных для .NET 4.7.2 или выше.|
|Область|Дополнительный номер|
|Версия|4.7.2|
|Тип|Изменение целевой платформы|
