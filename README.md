import {ChartModule} from 'angular2-highcharts';
import {HighchartsStatic} from 'angular2-highcharts/dist/HighchartsService';

declare var require: any;
export function highchartsFactory() {
    const hc = require('highcharts/highstock');
    const dd = require('highcharts/modules/exporting');
    dd(hc);
    return hc;
}

//Section: Imports
imports:[ChartModule],

//Section: Providers
providers:[
        ...
	{
		provide: HighchartsStatic,
		useFactory: highchartsFactory
	}
]
