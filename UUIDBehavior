<?php

namespace mootensai\behaviors;

use yii\base\Behavior;
use yii\db\ActiveRecord;

class UUIDBehaviors extends Behavior {
    /**
     * Field/Column yang akan diisi UUID
     * Default -> id
     * @var type 
     */
    public $column = 'id';

    /**
     * Override event() 
     * memasukkan method beforeSave() kedalam komponen ActiveRecord::EVENT_BEFORE_INSERT  
     * @return type
     */
    public function events() {
        return[
            ActiveRecord::EVENT_BEFORE_INSERT => 'beforeSave',
        ];
    }

    /**
     * set beforeSave() -> UUID data
     */
    public function beforeSave() {
        $this->owner->{$this->column} = $this->owner->getDb()->createCommand("SELECT REPLACE(UUID(),'-','')")->queryScalar();
    }

}
