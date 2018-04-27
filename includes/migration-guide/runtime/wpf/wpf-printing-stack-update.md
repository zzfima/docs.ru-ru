### <a name="wpf-printing-stack-update"></a>Обновления стека печати WPF

|   |   |
|---|---|
|Подробные сведения|API-интерфейсы WPF для печати, использующие <xref:System.Printing.PrintQueue?displayProperty=name>, теперь вызывают API пакета печати документа Windows вместо устаревшего API печати XPS. Это изменение внесено в целях повышения удобства обслуживания. Ни пользователи, ни разработчики не должны заметить какие-либо изменения в поведении или использовании API. Новый стек печати по умолчанию активируется при работе с обновлением Windows 10 Creators Update. Старый стек печати по-прежнему будет работать в предыдущих версиях Windows, как и раньше.|
|Предложение|Чтобы использовать старый стек в Windows 10 Creators Update, задайте значение <code>UseXpsOMPrinting</code> REG_DWORD в разделе реестра <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> равным <code>1</code>.|
|Область|Пограничный случай|
|Версия|4.7|
|Тип|Среда выполнения|

