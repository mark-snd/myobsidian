CMD75만 적용되도록 하려면 이 키보드의 product_id와 vendor_id 값을 넣어야 한다.  
해당 값은 Karabiner-EventViewer app에서 확인할 수 있다.
 
{  
"description": "Page_down to cmd + right arrow, Page_up to cmd + left arrow",  
"manipulators": [  
{  
"conditions": [  
{  
"identifiers": [  
{  
"product_id": 16401,  
"vendor_id": 12625  
}  
],  
"type": "device_if"  
}  
],  
"from": {  
"key_code": "page_down",  
"modifiers": { "optional": ["shift"] }  
},  
"to": [  
{  
"key_code": "right_arrow",  
"modifiers": ["command"]  
}  
],  
"type": "basic"  
},  
{  
"conditions": [  
{  
"identifiers": [  
{  
"product_id": 16401,  
"vendor_id": 12625  
}  
],  
"type": "device_if"  
}  
],  
"from": {  
"key_code": "page_up",  
"modifiers": { "optional": ["shift"] }  
},  
"to": [  
{  
"key_code": "left_arrow",  
"modifiers": ["command"]  
}  
],  
"type": "basic"  
}  
]  
}