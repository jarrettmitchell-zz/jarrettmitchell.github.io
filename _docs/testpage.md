---
title: Test New
tags:
---

<div class="calculator" data-calc-id="gwKfC3Ped4zDxshsM"></div>
<script type="text/javascript" id="convertcalculator-embedder-Dq3t2Q8XB5iNjmmR9" class="convertcalculator-async-script-loader">
  (function() {
    function async_load(){
      var s = document.createElement("script");
      s.type = "text/javascript";
      s.async = true;
      var url = 'https://app.convertcalculator.co/embed.js';
      s.src = url + ( url.indexOf("?") >= 0 ? "&" : "?") + "ref=" + encodeURIComponent(window.location.href);
      var embedder = document.getElementById('convertcalculator-embedder-Dq3t2Q8XB5iNjmmR9');
      embedder.parentNode.insertBefore(s, embedder);
    }
    if (window.attachEvent)
      window.attachEvent("onload", async_load);
    else
      window.addEventListener("load", async_load, false);
  })();
</script>

<!DOCTYPE html>
<head>

<script src="jquery-2.1.3.min.js"></script>
<script src="jquery.scrollTo.min.js"></script>

<script src="svg.js"></script>
<script src="../dist/flowsvg.js"></script>


<style>
a:hover {
    text-decoration:underline;
}
</style>
</head>
<body>
	<h1>RCUK flow chart</h1>
<div id="drawing" style="margin-left:10px"></div>

<script type="text/javascript">
///////////////////// start flow chart ////////////////////////////////////////////////////////////

    flowSVG.draw(SVG('drawing').size(900, 900));
    flowSVG.config({
        //interactive: true,
        //showButtons: true,
        connectorLength: 60,
        //scrollto: true,
		//scrollOffset: 300
    });
    flowSVG.shapes(
        [
            {
			label: 'knowPolicy',
			type: 'decision',
			text: [
				'Do you know the ',
                'Open Access policy',
                'of the journal?'
			],
			yes: 'hasOAPolicy',
			no: 'checkPolicy'
		}, 
      {
			label: 'hasOAPolicy',
			type: 'decision',
			text: [
				'Does it have Open',
                'Access paid option or is it an',
                ' Open Access journal?'
			],
			yes: 'CCOffered',
			no: 'canWrap'
		}, 
		{
			label: 'CCOffered',
			type: 'decision',
			text: [
                'Creative Commons',
                'licence CC-BY offered?'
            ],
            yes: 'canComply',
            no: 'canWrap'
            
		},
        {
            label: 'canComply',
            type: 'finish',
            text: [
                'Great. '
            ],
          links: [
              {
                  text: 'Apply for funding', 
                  url: 'http://www2.warwick.ac.uk/services/library/staff/research/open-access/apply-for-open-access-funding/', 
                  target: '_blank'
              }
          ],
          tip: {title: 'REF 2020 Note',
          text:
          [
              'You must put your',
              'accepted version in WRAP',
              'within 3 months of',
              'acceptance.'
          ]}
        },
		{
			label: 'canWrap',
			type: 'decision',
			text: [
                'Can you go "green"',
                'and archive in WRAP?'
               
            ],
            inNode: 't',
            yes: 'depositInWrap',
			no: 'doNotComply'
		}, 
        {
            label: 'doNotComply',
            type: 'finish',
            text: [
                'You do not comply at all. ',
                'Is this the only journal you',
                'want to use? Could you',
                'choose another journal?'
            ],
            tip: {title: 'REF 2020 Note',
            text:
            [
                'If you have to go this route',
                'you must log details and',
                'exception in WRAP within',
                '3 months of acceptance',
                'to comply.'
            ]}
        }, 
         // remove
        /*      
        {
           
			label: 'checkGreen',
			type: 'process',
			text: [
                'Check the journal\'s policy',
                'on the green route'
            ],
			next: 'journalAllows',
		}, 
        */
        /*
        {
            // remove
            label: 'journalAllows',
            type: 'decision',
            text: ['Does the journal allow this?'],
            yes: 'checkTimeLimits',
            no: 'cannotComply',
            orient: {
                yes:'r',
                no: 'b'
            }
            
        },
        */
        /*
        {
            // Remove
			label: 'checkTimeLimits',
			type: 'process',
			text: [
                'Make sure the time limits',
                'acceptable',
                '6 months STEMM',
                '12 month AHSS'
            ],
            next: 'depositInWrap'
        },
        */
        /*
        {
            
            // remove
            label: 'cannotComply',
            type: 'finish',
            text: [
                'You cannot comply with',
                'RCUK policy. Contact ',
                'journal to discuss or',
                'choose another'
            ],
            tip: {title: 'REF 2020 Note',
            text:
            [
                'Deposit in WRAP if',
                'time limits acceptable. If',
                'journal does not allow at all',
                'an exception record will',
                'have to be entered',
                'in WRAP, if you feel this is',
                'most appropriate journal.'
            ]}
        },
        */
        {
            label: 'depositInWrap',
            type: 'finish',
            text: [
                'Make sure the time limits',
                'acceptable:',
                '6 months STEM',
                '12 month AHSS'
            ],
			links: [
              {
                  text: 'Submit to WRAP', 
                  url: 'http://www2.warwick.ac.uk/services/library/staff/research/repositories-at-warwick/wrap/submit/'
              }
          ],
            tip: {title: 'REF 2020 Note',
            text:
            [
                'You must put your',
                'accepted version in WRAP',
                'within 3 months of',
                'acceptance. If time limits',
                'comply with RCUK they',
                'comply for the REF too.'
            ]}
        },
		{
			label: 'checkPolicy',
			type: 'process',
			text: [
				'Check journal website/'
			],
            links: [
                {
                    text: 'Contact the Library/', 
                    url: 'mailto:openaccessfunds@warwick.ac.uk'
                },
                {
                    text: 'SHERPA FACT/ROMEO ', 
                    url: 'http://www.sherpa.ac.uk/romeo/index.php', 
                    target: '_blank'
                }
            ],
			next: 'hasOAPolicy'
        }
    ]);
</script>
</body></html>
