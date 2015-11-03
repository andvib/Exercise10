#include <linux/module.h>
#include <linux/kernel.h>
#include <linux/proc_fs.h>

static struct proc_dir_entry *dir;

int procfile_read(char *buffer, char **buffer_location, off_t offset,
				  int buffer_length, int *eof, void *data){
	if (offset > 0){
		return 0;
	}else{
		return sprintf(buffer, "Hello world\n");
	}
}

int init_module(void){
	printk(KERN_INFO "Proc Entry! \n");

	dir = create_proc_entry("asd", 0644, NULL);
	dir -> read_proc = procfile_read;

	return 0;
}

void cleanup_module(void){
	printk(KERN_INFO "Goodbye World! \n");
	remove_proc_entry("asd", NULL);
}
