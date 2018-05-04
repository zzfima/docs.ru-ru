### <a name="multiple-items-in-a-single-tablelayoutpanel-cell-may-be-rearranged"></a>Можно упорядочить несколько элементов в одной ячейке TableLayoutPanel

|   |   |
|---|---|
|Подробные сведения|Если в .NET Framework 4.5 несколько элементов помещаются в одну и ту же ячейку <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name>, они могут отображаться в порядке, отличном от порядка отображения в .NET Framework 4.0.|
|Предложение|Это поведение было восстановлено в обновлении обслуживания для .NET Framework 4.5. Чтобы устранить эту проблему, обновите .NET Framework 4.5 или выполните обновление до .NET Framework 4.5.1 или более поздней версии. Кроме того, избегайте неоднозначных случаев, когда несколько элементов находятся в одной и той же ячейке <xref:System.Windows.Forms.TableLayoutPanel?displayProperty=name>.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.Forms.TableLayoutControlCollection.Add(System.Windows.Forms.Control%2CSystem.Int32%2CSystem.Int32)?displayProperty=nameWithType></li></ul>|
|Анализаторы|<ul><li>CD0098</li></ul>|

