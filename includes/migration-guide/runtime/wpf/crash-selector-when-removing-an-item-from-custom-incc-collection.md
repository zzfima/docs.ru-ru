### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Сбой в селекторе при удалении элемента из пользовательской коллекции INCC

|   |   |
|---|---|
|Подробные сведения|<code>T:System.InvalidOperationException</code> может возникнуть в следующих сценариях:<ul><li>ItemsSource для <code>T:System.Windows.Controls.Primitives.Selector</code> является коллекцией с пользовательской реализацией <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>Выбранный элемент удаляется из коллекции.</li><li>Для <code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> установлено <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = –1 (что указывает на неизвестную позицию).</li></ul>Стек вызова исключения начинается в System.Windows.Threading.Dispatcher.VerifyAccess() в System.Windows.DependencyObject.GetValue(DependencyProperty dp) в System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element) Это исключение может возникнуть в .Net 4.5, если у приложения несколько потоков Dispatcher. В .Net 4.7 исключение также может возникнуть в приложениях с одним потоком Dispatcher. Проблема устранена в .Net 4.7.1.|
|Предложение|Выполните обновление до .NET 4.7.1.|
|Область|Дополнительный номер|
|Версия|4.7|
|Тип|Среда выполнения|

