## Cuztom Helper

This class can be used to quickly register Custom Post Types, Taxonomies and Meta Boxes within your Wordpress projects.

**Version:** 0.2.1  
**Requires:** 3.0+  
**Tested up to:** 3.3  

## Basic usage

Include the class.
	
	include( 'cuztom_helper.php' );
   
Register the Post Type.
	
	$book = new Custom_Post_Type( 'Book' );
	
We can pass some arguments and labels as second and third parameter to overwrite the defaults.

	$book = new Custom_Post_Type( 'Book', 
				array( 'supports' => array( 'title', 'editor', 'excerpt' ) ),
				array( 'plural' => 'Little Books' )
			)
	
### Add Custom Taxonomies
	
To add Custom Taxonomies, simply call this method.

	$book->add_taxonomy( 'Author' );
			
You can also call this as a seperate class like this.

	$taxonomy = new Cuztom_Taxonomy( 'Author', 'post' ) )

### Add Meta Boxes
	
Add Meta Boxes.

	$book->add_meta_box( 
		'Book Info', 
		array(
			array(
				'name' 			=> 'author',
				'label' 		=> 'Author',
				'description'	=> 'Just a little description',
				'type'			=> 'text'
			),
			array(
				'name' 			=> 'year_written',
				'label' 		=> 'Year written',
				'description'	=> 'Just a little description',
				'type'			=> 'text'
			)
		)
	);
	
## Todo
* Todo: Cuztom::uglify needs to convert all strang characters to underscores

## Changelog

### 0.2.1
* WYSIWYG editor is now enabled
* Todo: Cuztom::uglify needs to convert all strang characters to underscores

### 0.2
* Seperated classes for Post Type, Taxonomy and Meta Box
* Support for PHP versions below 5.3
* Multiple field types added: [ text, textarea, checkbox, yes/no, select, checkboxes, radio, image ]
* Todo: Cuztom::uglify needs to convert all strang characters to underscores
* Todo: WYSIWYG is still a normal textarea, but needs to be converted to a WYSIWYG editor

### 0.1
* First release, based on my tutorial on wp.tutsplus.com