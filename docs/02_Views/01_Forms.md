**VieAssociative** provide some syntax sugar for creating forms with fiew lines

## Input

Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu. In enim justo, rhoncus ut, imperdiet a, venenatis vitae, justo. Nullam dictum felis eu pede mollis pretium.

<pre>
@input = array(
        'id'=>'',
		'form' => array(
            'placeholder'=>'',
            'class' => '',
    		'data-original-title'=>'',
		)
    )
@
{{ SiteHelpers::create_input($input) }}
</pre>

## Checkbox

Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem. Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu. In enim justo, rhoncus ut, imperdiet a, venenatis vitae, justo. Nullam dictum felis eu pede mollis pretium.
<pre>
	@input = array(
        'id'=>'',
        'label'=>'',
        'name'=> '',
        'data-toggle'=> '',
        'form' => array(
            '1'=>array(
                'value'=>'true',
                'text'=>'',
            ),
        )
    )@
    {{SiteHelpers::create_checkbox($input)}}
</pre>


## Radio

Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa. Cum sociis natoque penatibus cu. In enim justo, rhoncus ut, imperdiet a, venenatis vitae, justo. Nullam dictum felis eu pede mollis pretium.
- data-toggle On true, display specific id

<pre>
@input = array(
    'id'=>'',
    'label'=>'',
    'name'=> '',
    'data-toggle'=> '',
    'form' => array(
        '1'=>array(
            'value'=>'true',
            'text'=>'',
        ),
        '2'=>array(
            'value'=>'false',
            'text'=>'',
            'checked'=>true,
        ),
    )
)@
{{SiteHelpers::create_radio($input)}}
</pre>