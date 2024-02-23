# Relation père fils -> dans le model du père
    protected $table = 'projects';
    // a project can have multiple tasks
    public function tasks(): HasMany
    {
        return $this->hasMany(Task::class);
    } ->model père 
      // each task belongs to a single project
    public function project(): BelongsTo
    {
        return $this->belongsTo(Project::class);
    }-> model fils

# un ascenseur
    public function getCreatedAttribute()
    {
        return $this->created_at->diffForHumans();
    }
    En fonction, il existe une logique qui s'exécutera pour modifier l'enregistrement de la base de données déjà récupéré.get<WordsInCamelCase>Attribute()
    
    Dans notre cas, la getCreatedAttribute()fonction renverra un décalage horaire convivial et lisible entre l'heure actuelle et l'heure donnée. Par exemple, "il y a 3 minutes" ou "il y a 4 mois" .