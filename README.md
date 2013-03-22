node-euvies
===========

Resolve EU VAT identification numbers to company details.

How to use
===========

    var euVies = require('euvies');
    euVies.checkVat({countryCode: "PL", vatNumber: "5842656844"}, function(err, res) {
      if(err) return console.log(err);
      return res;
    });

Return:

    { countryCode: 'PL',
    vatNumber: '5842656844',
    requestDate: '2013-03-23+01:00',
    valid: true,
    name: 'DAMIAN KACZMAREK',
    address: [ 'xxx', 'xxx' ] }

Alternative:

    euVies.checkVat("PL5842656844", callback);
    
Notes:
* First check takes longer due to need to create a WSDL client.
* Invalid country will yield an error, otherwise a proper country and bad ID returns no error but an object with `valid` set to false.
