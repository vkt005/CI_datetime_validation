###################
What is CI_DateTime validator
###################

CI_DateTime validator is a CodeIgniter library intended to validate any date time against you supplied format,
date time validation is painfull process, specially in the case of API development. In which you have to take care of 
format Ex.(mm-dd-yy H:i:s) and as validity of date in that particular format 

Example - 12-01-2016 is Valid format(mm-dd-yy) while 13-01-2016 Becomes invalid becuse month cann't exceed more than 12.

*******************
validation format
*******************
1 - d-m-y  or d-m-Y or Y-m-d or m-d-y or m-d-Y
                  or
2-  d-m-y H:i:s  or d-m-Y H:i:s or Y-m-d H:i:s or m-d-y H:i:s or m-d-Y h:i:s
			      or
			      Any other valid date format

*******************
Release Information
*******************

This repo contains in-development code V1.0


*******************
Server Requirements
*******************

PHP version 5.6 or newer is recommended.

It should work on 5.3.7 as well, but we strongly advise you NOT to run
such old versions of PHP, because of potential security and performance
issues, as well as missing features.

************
Installation
************

download file MY_Form_validation.php and put in your projects application/libraries folder or 
copy and replace dowonload application folder with your it will not harm your previous files it will only add 1 files to your application/libraries directory


************
 USE
************
In your controller file

<?php defined('BASEPATH') OR exit('No direct script access allowed');

class User extends CI_Controller {

	public function __construct()
	{
		parent::__construct();
		$this->load->library('form_validation');
	}

	function register() {
    $this->form_validation
   		  **->set_rules('date_time', 'datetime', 'required|datetime[Y-m-d H:i:s]');**
    	  ->set_rules('first_name', 'First Name', 'required')
          ->set_rules('last_name', 'Last Name', 'required')
          ->set_rules('email', 'Email', 'required')
          ->set_rules('password', 'Password', 'required');
                              
        if ($this->form_validation->run() != FALSE) {
 
 // put your code here            
       
        } else
            echo validation_errors();
    }
}
?>




*******
License
*******

FREE*