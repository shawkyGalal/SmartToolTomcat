[Back to Index](./index.md)


## Customize WPT component:

WPT component can be customized by web developers through customize options.

There are many [Customize Options](#customizeoptions), all of which can be passed
in parameters when creating the WebPivotTable object on your page or can be set 
by API after WebPivotTable object had been created.

### Pass in customize options when create WebPivotTable object

    var myOptions = {
        uiFlags: {
            openWptBtn: 0,
            saveWptBtn: 0
        }
    };
    var webPivotTable = new WebPivotTable({
        customOptions:myOptions
    },"wpt-container");

### Set customize options for existing WebPivotTable object

Even after WebPivotTable object being created, you can still change options:

    var myOptions = {
        uiFlags: {
            openWptBtn: 0,
            saveWptBtn: 0
        }
    };
    webPivotTable.setOptions(myOptions);


<h3 id="customizeoptions">All Customize Options</h3>

    var defaultOptions = {
    
        locale: 'en',        // Current language locale
                             // it should be set to one of values in below availableLocals

        availableLocales: ['en','zh','tr','es','pt','it'],
                             // Selectable language locales for users to switch languages
                             // possible locales like: 'en','zh','tr', 'es','pt',‘fr','de','ar',
                             // 'ru','it', 'nl','el','he','hi','hu','sv','ko','ja'

        leavePageWarning: 1, // When user leave page, whether show a warning or not

        uiFlags: {           // A set of flags to control User Interface

            switchViewBtn: 1,     // show/hide TopBar view switch buttons
            dataSourceBtn: 1,     // show/hide DataSource View Button
            pivotTableBtn: 1,     // show/hide PivotTable View Button
            reportBtn: 1,         // show/hide Report View Button

            newWptBtn: 1,         // show/hide TopBar "Create New WPT" button
            openWptBtn: 1,        // show/hide TopBar "Open WPT" button
            saveWptBtn: 1,        // show/hide TopBar "Save WPT" button

            navPaneBtn: 1,        // show/hide TopBar "Show/Hide Navigation Panel" button
            userBtn: 1,           // show/hide TopBar "Users" dropdown button
            settingBtn: 1,        // show/hide TopBar "Setting" button
            languageSwitchBtn: 1, // show/hide TopBar 'Language' dropdown button

            helpBtn: 1,           // show/hide TopBar 'Help' button
                                  // Only works for Component edition, Will always show for free edition
            aboutBtn: 1,          // show/hide TopBar 'About' button
                                  // Only works for Component edition, Will always show for free edition

            memoryTab: 1,         // show/hide Load data view "Memory" Tab
            olapTab: 1,           // show/hide Load data view "OLAP" Tab
            internetLinkTab: 1,   // enable/disable Load data or wpt from "Internet Link"
            cloudDriveBtn: 1,     // enable/disable Load data or wpt from "Cloud Drive"
            localDriveTab: 1,     // enable/disable Load data or wpt from "Local Drive"
            webServiceTab: 1,     // enable/disable Load data or wpt from "Web Service"
            googleSpreadSheetTab: 1, // enable/disable Load data from "Google Spreadsheet"
            copyPasteTab: 1,      // enable/disable Load data or wpt from "Copy & Paste"

            localSaveTab: 1,      // show/hide Save WPT dialog "Save to local" Tab
            serverSaveTab: 1,     // show/hide Save WPT dialog "Save to Server" Tab

            newSourceBtn: 1,      // show/hide new source button
            newSheetBtn: 1,       // show/hide new sheet button
            newReportBtn: 1,      // show/hide new report button
            renameSourceBtn: 1,   // show/hide rename source button
            renameSheetBtn: 1,    // show/hide rename sheet button
            renameReportBtn: 1,   // show/hide rename report button

            changeSourceBtn: 1,   // show/hide change source button
            refineBtn: 0,         // show/hide refine dialog button


            sourceBarMenuBtn: 1,  // show/hide menu button on source bar
            sourceBarCustomize: 1, // show/hide customize button on source bar
            sourceBarExport: 1,    // show/hide export button on source bar


            calculatedFieldBtn: 1, // show/hide calculated field button
            categoryFieldBtn: 1,  // show/hide category field button
            sheetBarMenuBtn: 1,   // show/hide menu button on sheet bar
            sheetBarMdxBtn: 1,    // show/hide MDX button on sheet bar
            sheetBarFieldsList: 1, // show/hide fields List on sheet bar
            sheetBarPivotFields: 1,  // show/hide Pivot fields on sheet bar
            sheetBarCustomize: 1, // show/hide customize button on sheet bar
            sheetBarExport: 1,    // show/hide export button on sheet bar

            reportBarMenuBtn: 1,  // show/hide menu button on report bar
            reportBarCustomize: 1, // show/hide customize button on report bar
            reportBarExport: 1,    // show/hide export button on report bar

            drillThroughCustomize: 1, // show/hide customize button on drillThrough bar
            drillThroughExport: 1,    // show/hide export button on drillThrough bar


            exportToExcel: 1,     // support "Export to Excel"
            exportToCsv: 1,       // support "Export to Csv"
            exportToHtml: 1,      // support "Export to HTML"
            exportToPdf: 1,       // support "Export to PDF"
            exportToPng: 1,       // support "Export to PNG"
            exportToJpeg: 1,      // support "Export to JPEG"
            exportToGif: 1,       // support "Export to GIF"

            drillThroughByDoubleClick: 0,  // doubleclick or click to drill through pivot grids
            oldDialogStyle: 0,    // use dijit.Dialog instead of dojox.dialog
            deferLayoutExcludeFilter: 0,   // exclude field sort/filter from defer layout update
            defaultToDistinctCount: 0,     // Default statistic function of String field to distinct count

            zoomBtn: 1,           // show/hide "Zoom" menu
            fullScreenBtn: 1      // enable/disable "Full Screen" mode
        },

        defaultView: "PIVOTTABLE",   // Default view: 'DATASOURCE', 'PIVOTTABLE', 'REPORT'

        navigationPane: {            // Navigation Panel
            show: 1,                 // show/hide: 1/0
            position:'right',        // position: 'left', 'top', 'right', 'bottom'
            stacked: 0,              // stack fields area or not: 1/0
            width:300,               // width, only for left and right
            height:200               // height, only for top and bottom
        },

        fileLinks:[
            //{
            //    type: "WPT",
            //    url: "http://demo.webpivottable.com/json/sample91.wpt",
            //    label: "Predefined small CSV WebPivotTable file"
            //},{
            //    type: "CSV",
            //    url: "http://demo.webpivottable.com/json/example.csv",
            //    label: "USA Selection Poll Data (Total 4,000 records)"
            //},{
            //    type: "EXCEL",
            //    url: "http://demo.webpivottable.com/json/example.xls",
            //    label: "USA Selection Poll Data (Total 4,000 records)"
            //},{
            //    type: "EXCEL",
            //    url: "http://demo.webpivottable.com/json/sales.xls",
            //    label: "Sales Sample Data (Total 2,823 records)"
            //},{
            //    type: "EXCEL",
            //    url: "http://demo.webpivottable.com/json/sales.xlsx",
            //    label: "Sales Sample Data (Total 2,823 records)"
            //},{
            //    type: "WSWPT",
            //    url: "http://demo.webpivottable.com/json/sample91.wpt",
            //    label: "Predefined small CSV WebPivotTable file"
            //},{
            //    type: "WSDATA",
            //    url: "http://demo.webpivottable.com/json/sample91.wpt",
            //    label: "Predefined small CSV WebPivotTable file"
            //},{
            //    type: "GSS",
            //    url: "https://docs.google.com/spreadsheet/pub?key=0Alkl5EEsxBwBdDFLV2Q4a1NWMmw1TXZBRlFMZ1Rxd0E&output=html",
            //    label: "USA Selection Poll Data (Total 4,000 records)"
            //},{
            //    type: "OLAP",
            //    url: "http://sampledata.infragistics.com/olap/msmdpump.dll",
            //    label: "Sample Microsoft Analysis Service"
            //},{
            //    type: "OLAP",
            //    url: "http://52.37.24.202:8080/mondrian/xmla",
            //    label: "Sample Mondrian OLAP Server"
            //}
        ],

        customizeNew: {           // If enabled, click "Create New Wpt" button will not open dialog.
                                  // Integration developers can hook their own handler in callback
            enabled: false,       // enable/disable this hook
            callback: function(webPivotTable){} // customize handler when click "Create New Wpt" button
        },

        customizeOpen: {          // If enabled, click "Open Wpt" button will not open dialog.
                                  // Integration developers can hook their own handler in callback
            enabled: false,       // enable to call user customize save wpt UI
            callback: function(webPivotTable){} // customize handler when click "Open Wpt" button
        },

        customizeSave: {          // If enabled, click "Save Wpt" button will not open dialog.
                                  // Integration developers can hook their own handler in callback
            enabled: false,       // enable to call user customize save wpt UI
            ignoreData: false,    // whether the passed wptString include data or not
            callback: function(webPivotTable, wptString){}
                                  // customize handler when click "Save Wpt" button
        },

        customizeButtons: [       // Add Customize buttons on top bar
            //{
            //    label: "Customize",
            //    title: "A customize button to do something funncy",
            //    click: function (evt){
            //        alert("haha, I am clicked!"+this);
            //    }
            //}
        ],

        filepicker:{
            key:''                // filepicker application key
        },

        decimalPoint: '.',        // decimal point charactor: '.', ','
        thousandsSep: ',',        // thousands separator: ',' '.', ' '

        sourceDataMaxRows: 100000,  // maximum supported rows of source data
        zoomScaleStep: 0.05,        // when zoom in/out, this is the scale for each step

        reportCssFile: './brightsea/wpt/wptReport.css',
                                  // Report CSS file path
                                  // If integration developer changed th file structure of Component,
                                  // this should be set to point to correct path.

        webServiceTimeout: 10000,  // Web Service call timeout setting

        olap:{
            drillThroughMaxRows: 1000,  // Max return rows for each drill through call
            sync : 0,                   // Synchroize / Asynchorize call
            timeout : 300000,           // Timeout for xmla call
            xmlaProxyEnabled: 1,        // enable/disable Xmla Proxy 1/0
            xmlaProxy: '/wpt/xmlaProxy' // Server proxy for cross domain xmla access
        },

        exporting: {
            pdf: {
                paperMarginTop: '1cm',
                paperMarginLeft: '1cm',
                paperMarginBottom: '1cm',
                paperMarginRight: '1cm',
                paperFormat: 'A4', //'A3', 'A4', 'A5', 'Legal', 'Letter', 'Tabloid'. 'Custom'
                paperOrientation: 'portrait',  //'portrait', 'landscape'
                paperWidth: '600px',
                paperHeight: '600px',
                headerHeight: '1cm',
                header: '',
                footerHeight: '1cm',
                footer: '',
                zoomFactor: 1
            }
        },

        server: {
            helpUrl:'http://webpivottable.com/documents',
            fileProxyEnabled: 1,          // enable/disable file Proxy 1/0
            fileProxy: '/wpt/fileProxy',  // Server proxy for cross domain file acess
            generatePdf: '/wpt/generatePdf'  // Server generate PDF service
        },


        csvGrid:{
            cellWidth: 120,
            cellHeight: 21
        },

        source: {                  // Default options for each new source
            grid: {
                cellWidth: 120,
                cellHeight: 21
            }
        },

        report: {                  // Default options for each new report
            title: {
                enabled: true,
                align: 'center',          // left, center, right
                paddingTop: 10,
                paddingRight: 10,
                paddingBottom: 10,
                paddingLeft: 10,
                fontSize: 28,
                fontWeight: "bold"
            },
            component: {
                title: {
                    enabled: true,
                    align: 'left',            // left, center, right
                    paddingTop: 10,
                    paddingRight: 10,
                    paddingBottom: 10,
                    paddingLeft: 10,
                    fontSize: 24,
                    fontWeight: "bold"
                }
            }
        },

        sheet:{                    // Default options for each new sheet

            chartFirst: 0,          // show chart at top/left? 0/1
            pivotLayout: '1',       // Pivot Grid and chart layout
                                    // 0 -- tile horizontal, 1 -- tile vertical,
                                    // 2 -- grid only,  3 -- chart only
            expandRows: 1,          // Expand/collapse All rows
            expandCols: 1,          // Expand/Collapse All columns
            nonEmpty: 1,
            mdx: '',

            grid:{
                showSigns: 1,
                showRowTotals: 1,
                showColTotals: 1,
                showRowSubtotals: 1,
                showColSubtotals: 1,
                compactForm: 1,
                rowHeaderWidth: 200,
                cellWidth: 100,
                cellHeight: 25,
                theme: 'wpt-default'
            },
            chart:{
                width: 500,
                height: 300,

                high:{
                    theme: 'default', //default, grid, gray, skies, drak-blue, drak-green
                    chart:{
                        type:'column',  //column, bar, line, spline, area, areaspline, pie
                        options3d: {
                            enabled: false,
                            alpha: 15,
                            beta: 15,
                            depth: 50,
                            viewDistance: 25
                        }
                    },
                    credits: {
                        enabled:false
                    },
                    exporting: {
                        enabled:false
                    },
                    navigation:{
                        buttonOptions:{
                            align: 'right',   // left, center, right
                            verticalAlign: 'top' // top, middle, bottom
                        }
                    },
                    legend: {
                        enabled: true,
                        floating: false,
                        layout: 'vertical',  //horizontal, vertical
                        align: 'right',      // left, center, right
                        verticalAlign: 'middle', // top, middle, bottom
                        reversed: false
                    },
                    tooltip:{
                        enabled: true,
                        shadow: true
                    },
                    plotOptions: {
                        series:{
                            stacking: null //null, 'normal', 'percent'
                        }
                    },
                    xAxis: {
                        labels:{
                            enabled: true,
                            align:'left',  // left, center, right
                            rotation:45    // 0 -- 360
                        }
                    }
                }
            }
        }

    };
