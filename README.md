# How to set alternate row styling on listview based on span count?

This example demonstrates how to define alternate row color for grid elements based on its span count in listview.

## Sample

```xaml
        <Grid>
            <Grid.RowDefinitions>
                <RowDefinition Height="*"/>
            </Grid.RowDefinitions>
                
            <syncfusion:SfListView x:Name="listView" SelectionMode="Multiple" 
                                   ItemSpacing="1" ItemSize="150"
                                   ItemsSource="{Binding contactsinfo}">
                <syncfusion:SfListView.LayoutManager>
                    <syncfusion:GridLayout x:Name="grid" SpanCount="4" />
                </syncfusion:SfListView.LayoutManager>
                <syncfusion:SfListView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <ViewCell.View>
                                <Grid x:Name="grid" RowSpacing="0"
                                      BackgroundColor="{Binding .,Converter={StaticResource IndexToColorConverter},ConverterParameter={x:Reference Name=listView}}">
                                    <Grid.RowDefinitions>
                                        <RowDefinition Height="*" />
                                        <RowDefinition Height="1" />
                                    </Grid.RowDefinitions>
                                    <Grid RowSpacing="0">
                                        <Grid.ColumnDefinitions>
                                            <ColumnDefinition Width="Auto" />
                                        </Grid.ColumnDefinitions>

                                        <Grid Grid.Column="1"
                          RowSpacing="1"
                          Padding="10,0,0,0"
                          VerticalOptions="Center">
                                            <Grid.RowDefinitions>
                                                <RowDefinition Height="*" />
                                                <RowDefinition Height="*" />
                                            </Grid.RowDefinitions>

                                            <Label LineBreakMode="NoWrap" Text="{Binding ContactName}"/>
                                            <Label Grid.Row="1" Grid.Column="0"
                             TextColor="#474747"
                             LineBreakMode="NoWrap"
                             Text="{Binding ContactNumber}">

                                            </Label>
                                        </Grid>
                                    </Grid>
                                </Grid>
                            </ViewCell.View>
                        </ViewCell>
                    </DataTemplate>
                </syncfusion:SfListView.ItemTemplate>
                
            </syncfusion:SfListView>
        </Grid>

```

See [How to set alternate row styling on listview based on span count?](https://www.syncfusion.com/kb/8448/how-to-achieve-the-alternate-row-styling-in-sflistview) for more details.

## Requirements to run the demo

* [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/) or [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)
* Xamarin add-ons for Visual Studio (available via the Visual Studio installer).

## Troubleshooting

### Path too long exception

If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.
